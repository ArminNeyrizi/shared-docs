در توسعه برنامه‌های کاربردی با Node.js، استفاده از الگوی معماری **لایه‎‌بندی شده (Layered Architecture)** یکی از بهترین روش‌ها برای رعایت اصول OOP و حفظ قابلیت نگهداری (Maintainability) کد است.

در اینجا این سه لایه را بررسی می‌کنیم و یک مثال ساده برای درک جریان داده می‌آوریم.

---

### ۱. معرفی لایه‌ها

*   **Controller (لایه کنترل‌کننده):** نقطه ورودی درخواست‌های HTTP است. وظیفه آن صرفاً دریافت درخواست (Request)، اعتبارسنجی اولیه، فراخوانی سرویس مربوطه و ارسال پاسخ (Response) به کاربر است.
*   **Service (لایه سرویس/تجارت):** قلب برنامه است. تمامی منطق‌های تجاری (Business Logic)، محاسبات پیچیده، و تصمیم‌گیری‌ها اینجا اتفاق می‌افتد. سرویس نباید بداند که داده‌ها چگونه در دیتابیس ذخیره می‌شوند.
*   **Repository (لایه مخزن):** تنها لایه‌ای است که با دیتابیس (ORM یا Query Builder) صحبت می‌کند. وظیفه آن فقط خواندن، نوشتن، آپدیت یا حذف داده‌ها (CRUD) است.

---
این سه لایه فقط برای **مرتب و قابل‌مدیریت کردن کد برنامه** استفاده می‌شوند. ساده‌تر توضیح می‌دهم:

فرض کن یک **فروشگاه آنلاین** داری و کاربر می‌خواهد یک محصول بخرد.

### Controller (کنترل‌کننده)
این لایه فقط **درخواست کاربر را می‌گیرد و جواب می‌دهد**.  
مثل **مسئول پذیرش**.

مثال:
- کاربر دکمه «خرید» را می‌زند
- درخواست به Controller می‌رسد
- Controller درخواست را به Service می‌فرستد

Controller خودش کار پیچیده انجام نمی‌دهد.

مثال ساده:

```python
def buy_product(request):
    order = order_service.create_order(request.user_id, request.product_id)
    return order
```

---

### Service (سرویس)
این **مغز برنامه** است.  
تمام تصمیم‌ها و منطق اصلی اینجاست.

مثلاً:
- آیا محصول موجود است؟
- آیا کاربر پول کافی دارد؟
- قیمت نهایی چقدر است؟

بعد از انجام این کارها، به Repository می‌گوید داده را ذخیره کند.

مثال:

```python
class OrderService:
    def create_order(self, user_id, product_id):
        product = product_repository.get(product_id)

        if product.stock == 0:
            raise Exception("محصول موجود نیست")

        return order_repository.create(user_id, product_id)
```

---

### Repository (ریپازیتوری)
این لایه فقط **با دیتابیس حرف می‌زند**.

کارهایش:
- گرفتن داده از دیتابیس
- ذخیره داده
- حذف داده
- آپدیت داده

مثال:

```python
class ProductRepository:
    def get(self, product_id):
        return db.products.find(product_id)
```

---

### یک مثال خیلی ساده از جریان کار

1️⃣ کاربر درخواست می‌دهد → **Controller**  
2️⃣ Controller می‌فرستد → **Service**  
3️⃣ Service برای گرفتن یا ذخیره داده می‌رود → **Repository**  
4️⃣ Repository با **Database** صحبت می‌کند

```
User
  ↓
Controller
  ↓
Service
  ↓
Repository
  ↓
Database
```
---
### چرا این کار را می‌کنند؟

چون اگر همه چیز در یک فایل باشد:
- کد خیلی شلوغ می‌شود
- تغییر دادن سخت می‌شود
- تست گرفتن سخت می‌شود

با این روش:
- هر بخش مسئول یک کار مشخص است.

---
### ۲. مثال کاربردی: ثبت نام کاربر (User Registration)

فرض کنید می‌خواهیم یک کاربر جدید ثبت کنیم.

#### لایه Repository (لایه دسترسی به داده)
```typescript
// userRepository.ts
class UserRepository {
  async save(userData: any) {
    // ارتباط با دیتابیس (مثلا Prisma یا TypeORM)
    return await db.user.create({ data: userData });
  }
}
```

#### لایه Service (لایه منطق تجاری)
```typescript
// userService.ts
class UserService {
  constructor(private userRepository: UserRepository) {}

  async registerUser(data: any) {
    // منطق تجاری: بررسی تکراری نبودن ایمیل، هش کردن پسورد و...
    const hashedPassword = await hash(data.password);
    return await this.userRepository.save({ ...data, password: hashedPassword });
  }
}
```

#### لایه Controller (لایه رابط وب)
```typescript
// userController.ts
class UserController {
  constructor(private userService: UserService) {}

  async handleRegister(req: Request, res: Response) {
    try {
      const user = await this.userService.registerUser(req.body);
      res.status(201).json(user);
    } catch (error) {
      res.status(400).json({ error: error.message });
    }
  }
}
```

---

### ۳. جریان داده (Data Flow)

جریان داده در این معماری به صورت یک‌طرفه و استاندارد است:

1.  **Request:** کاربر یک درخواست `POST /register` می‌فرستد.
2.  **Controller:** درخواست را می‌گیرد، آن را از طریق اعتبارسنجی (مثل Joi یا Zod) رد می‌کند. سپس `userService.registerUser` را صدا می‌زند.
3.  **Service:** منطق تجاری را اجرا می‌کند (مثل هش کردن پسورد). سپس `userRepository.save` را صدا می‌زند.
4.  **Repository:** کوئری مناسب را برای دیتابیس می‌سازد و نتیجه (داده ذخیره شده) را به سرویس بازمی‌گرداند.
5.  **Response:** سرویس نتیجه را به کنترلر برمی‌گرداند و کنترلر پاسخ نهایی (مثلاً کد 201) را به کاربر ارسال می‌کند.

### چرا این روش؟
*   **تست‌پذیری (Testability):** می‌توانید به راحتی لایه سرویس را بدون نیاز به دیتابیس واقعی (با Mock کردن Repository) تست کنید.
*   **تغییرپذیری:** اگر روزی تصمیم بگیرید دیتابیس خود را از MongoDB به PostgreSQL تغییر دهید، فقط لایه **Repository** تغییر می‌کند و هیچ تغییری در منطق تجاری (سرویس) یا کنترلرها نیاز نیست.
*   **خوانایی:** کدها تمیز، جدا از هم و دارای مسئولیت‌های مشخص (Single Responsibility Principle) هستند.

-----------

## ۱. چرا Dependency Injection؟
DI کمک می‌کند:

* وابستگی‌ها را از بیرون به کلاس‌ها تزریق کنید، نه اینکه کلاس‌ها خودشان بسازند.
* تست‌پذیری افزایش یابد.
* کد منعطف‌تر و قابل توسعه‌تر شود.

-----------

## ۲. بدون DI چه اتفاقی می‌افتد؟
اگر درون سرویس، Repository را new کنیم:

```ts
class UserService {
  private repo = new UserRepository();
}
```

این کار باعث می‌شود تغییر Repository یا تست کردن آن بسیار سخت شود.

-----------

## ۳. نمونه صحیح: استفاده از DI

### Repository  
```ts
// userRepository.ts
export class UserRepository {
  async save(userData) {
    return await db.user.create({ data: userData });
  }
}
```

### Service  
```ts
// userService.ts
import { UserRepository } from "./userRepository";

export class UserService {
  constructor(private userRepository: UserRepository) {}

  async registerUser(data) {
    const hashedPassword = await hash(data.password);
    return await this.userRepository.save({
      ...data,
      password: hashedPassword,
    });
  }
}
```

### Controller  
```ts
// userController.ts
import { UserService } from "./userService";

export class UserController {
  constructor(private userService: UserService) {}

  async handleRegister(req, res) {
    try {
      const user = await this.userService.registerUser(req.body);
      res.status(201).json(user);
    } catch (err) {
      res.status(400).json({ error: err.message });
    }
  }
}
```

-----------

## ۴. مرحله DI (مرحله ساخت و اتصال وابستگی‌ها)
در این مرحله، لایه‌ها در یک نقطه مرکزی (مثلاً app.js یا container.js) ساخته و به یکدیگر تزریق می‌شوند.

### Node.js IoC Container (ساده و دستی)

```ts
// container.js
import { UserRepository } from "./userRepository";
import { UserService } from "./userService";
import { UserController } from "./userController";

const userRepository = new UserRepository();
const userService = new UserService(userRepository);
export const userController = new UserController(userService);
```

### استفاده در روتر Express

```ts
// routes.js
import express from "express";
import { userController } from "./container";

const router = express.Router();

router.post("/register", (req, res) =>
  userController.handleRegister(req, res)
);

export default router;
```

----------

## ۵. نمودار جریان با DI

```
Request → Controller → Service → Repository → Database → Response
```

DI فقط کمک می‌کند این ارتباط‌ها **انعطاف‌پذیر، تست‌پذیر و تمیز** باشند.

----------

## ۶. مزایای DI در عمل
* تغییر Repository (مثلاً از MongoDB → PostgreSQL) بدون تغییر سرویس
* تست Unit بدون DB واقعی:
  - ایجاد Mock ساده  
  - تزریق Mock به سرویس
* Separation of Concerns کامل

### مثال واقعی Mock هنگام تست
```ts
class MockUserRepository {
  async save(data) {
    return { id: 1, ...data };
  }
}

const service = new UserService(new MockUserRepository());

test("register user", async () => {
  const user = await service.registerUser({ email: "a@b.com", password: "123" });
  expect(user.id).toBe(1);
});
```
اینجا:

- `MockUserRepository` یک **کلاس تقلبی** است (واقعی نیست).
- به جای اینکه واقعا بره تو دیتابیس ذخیره کنه،  
  متد `save` فقط یک شیء برمی‌گردونه:
  ```ts
  { id: 1, ...data }
  ```
- بعد این Repository تقلبی را می‌دی به:
  ```ts
  new UserService(new MockUserRepository())
  ```
  یعنی سرویس تو فکر می‌کند که با یک Repository واقعی صحبت می‌کند،  
  ولی در حقیقت با یک **نسخه تست / فِیکی** طرف است.

---

## 2. پس "mock" یعنی چی؟

**Mock** یعنی:  
یک **جایگزین تقلبی / مصنوعی** برای یک چیز واقعی، که فقط در **تست** استفاده می‌کنیم.

ویژگی‌ها:

- رفتار ساده و قابل پیش‌بینی دارد
- کارهای واقعی (مثل اتصال به دیتابیس، API، شبکه، فایل سیستم) را انجام نمی‌دهد
- فقط وانمود می‌کند (fake می‌کند) که آن کار انجام شده

به فارسی غیررسمی:  
**mock = نسخه جعلی / فیک / شبیه‌سازی شده برای تست**

---

## 3. چرا از Mock استفاده می‌کنیم؟

فرض کن `UserService` به این چیزها وابسته است:

- دیتابیس واقعی
- سرویس ایمیل
- سرویس SMS
- API بانک

وقتی می‌خواهی **منطق سرویس** را تست کنی:

- نمی‌خواهی هر بار واقعا به دیتابیس وصل شوی
- نمی‌خواهی هر بار واقعا ایمیل بفرستی
- نمی‌خواهی وابسته به اینترنت/شبکه باشی

پس می‌گویی:

> "به جای Repository واقعی، یک MockRepository ساده به سرویس بده  
> تا من ببینم منطق سرویس درست کار می‌کند یا نه."

---
## 4. در مثال چه اتفاقی می‌افتد؟

### بدون Mock (سناریو واقعی)
اگر Repository واقعی بود:

```ts
class UserRepository {
  async save(data) {
    // اینجا مثلا:
    // INSERT INTO users ...
    // و بعد برگرداندن user واقعی از دیتابیس
  }
}
```

- باید دیتابیس بالا باشد
- کانفیگ شود
- داده‌ها پاک شوند
- سرعت پایین‌تر می‌شود

### با Mock

```ts
class MockUserRepository {
  async save(data) {
    return { id: 1, ...data };
  }
}
```
- هیچ دیتابیسی وجود ندارد
- فقط تظاهر می‌کنیم که ذخیره شده
- همیشه `id = 1` برمی‌گردانیم
- تست سریع، ساده، بدون وابستگی

و در تست:

```ts
const user = await service.registerUser({ email: "a@b.com", password: "123" });
expect(user.id).toBe(1);
```

در اینجا تو می‌خواهی مطمئن شوی که:

- `registerUser` درست کار می‌کند
- سرویس به `repository.save` درست دیتا می‌دهد
- خروجی‌ای که برمی‌گردد همان چیزی است که انتظار داری

تو الان **منطق سرویس** را تست می‌کنی،  
نه **کارکرد دیتابیس** را.
## سوال ها
۱. چرا معماری لایه ای یکی از راهکار های خوب برای استفاده از OOP هست؟