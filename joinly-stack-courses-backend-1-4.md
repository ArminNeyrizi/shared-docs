
**prototype** یکی از مفاهیم پایه‌ای جاوااسکریپت است و برای **به‌اشتراک‌گذاری ویژگی‌ها و متدها بین objectها** استفاده می‌شود.

بیا ساده و مرحله‌ای بفهمیم.

---

# prototype چیست؟

در جاوااسکریپت هر **تابع سازنده (constructor)** یک property به نام **prototype** دارد.

این prototype یک **object** است که متدها و ویژگی‌هایی که باید بین همه‌ی instanceها مشترک باشند داخل آن قرار می‌گیرند.

---

# مثال ساده

```javascript
function User(name) {
  this.name = name;
}

User.prototype.sayHi = function() {
  console.log("Hi " + this.name);
};
```

ساخت object:

```javascript
const u1 = new User("Ali");
const u2 = new User("Sara");
```

حالا:

```javascript
u1.sayHi();
u2.sayHi();
```

خروجی:

```
Hi Ali
Hi Sara
```

نکته مهم:

متد `sayHi` داخل خود objectها نیست.

داخل اینجاست:

```
User.prototype
```

پس هر دو object از **یک متد مشترک** استفاده می‌کنند.

---

# چرا prototype مهم است؟

اگر متد را داخل constructor بگذاریم:

```javascript
function User(name) {
  this.name = name;

  this.sayHi = function() {
    console.log("Hi " + this.name);
  };
}
```

هر بار که object ساخته می‌شود:

یک **کپی جدید از تابع** ساخته می‌شود.

```
u1 → sayHi()
u2 → sayHi()
```

❌ مصرف حافظه بیشتر

اما با prototype:

```
u1
u2
u3
   ↓
User.prototype.sayHi
```

✅ فقط یک تابع در حافظه

---

# prototype در پشت صحنه

وقتی می‌نویسی:

```javascript
const u1 = new User("Ali");
```

جاوااسکریپت این کار را می‌کند:

```
u1.__proto__ = User.prototype
```

پس ارتباط این است:

```
u1
 ↓
User.prototype
 ↓
Object.prototype
 ↓
null
```

این همان **Prototype Chain** است.

---

# وقتی property پیدا نشود چه می‌شود؟

مثال:

```javascript
console.log(u1.name);
```

جاوااسکریپت این مسیر را می‌رود:

1️⃣ داخل `u1`  
✅ پیدا شد

---

مثال دوم:

```javascript
u1.sayHi()
```

جاوااسکریپت:

1️⃣ داخل `u1`  
❌ نبود

2️⃣ داخل `User.prototype`  
✅ پیدا شد

---

# prototype در class

در ES6 وقتی می‌نویسیم:

```javascript
class User {

  constructor(name){
    this.name = name;
  }

  sayHi(){
    console.log("Hi " + this.name);
  }

}
```

در واقع پشت صحنه این می‌شود:

```javascript
User.prototype.sayHi = function(){
  console.log("Hi " + this.name);
}
```

پس:

> متدهای کلاس در **prototype** ذخیره می‌شوند.

---

# یک تصویر ذهنی ساده

فرض کن prototype مثل یک **کتابخانه مشترک** است.

```
u1 ----\
        → User.prototype → sayHi()
u2 ----/
u3 ----/
```

همه از یک جا استفاده می‌کنند.

---

✅ خلاصه کوتاه:

prototype یعنی:

- جایی برای نگهداری **متدهای مشترک**
- برای اینکه همه instanceها از آن استفاده کنند
- و جاوااسکریپت هنگام پیدا نکردن property در object، آنجا را بررسی می‌کند.

## ES6

در ES6 (سال 2015) جاوااسکریپت چیزی به نام **class** معرفی کرد تا ساخت **objectها** ساده‌تر و شبیه زبان‌هایی مثل Java و C# شود.

اما نکته مهم:

> Class در جاوااسکریپت در واقع فقط **syntactic sugar** روی Prototype و Constructor Function است.

یعنی پشت صحنه هنوز همان سیستم قبلی کار می‌کند.

---

# 1️⃣ تعریف Class

ساختار ساده یک کلاس:

```javascript
class Person {

}
```

معمولاً اسم کلاس با **حرف بزرگ** نوشته می‌شود:

```javascript
class Student {

}
```

---

# 2️⃣ constructor

در کلاس‌ها تابعی به نام **constructor** داریم که هنگام ساخت شیء اجرا می‌شود.

مثال:

```javascript
class Student {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
```

ساخت نمونه:

```javascript
const s1 = new Student("Ali", 20);
const s2 = new Student("Sara", 22);
```

حالا:

```
s1.name → "Ali"
s1.age → 20
```

✅ constructor همان نقش **Constructor Function** قدیمی را دارد.

---

# 3️⃣ Method در Class

در کلاس می‌توانیم **متد (تابع)** تعریف کنیم.

مثال:

```javascript
class Student {

  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  introduce() {
    console.log("My name is " + this.name);
  }

}
```

استفاده:

```javascript
const s1 = new Student("Ali", 20);

s1.introduce();
```

خروجی:

```
My name is Ali
```

نکته مهم:

متدهای کلاس در **prototype** قرار می‌گیرند، نه داخل خود object.

---

# 4️⃣ مقایسه Class با Function

### روش قدیمی (Constructor Function)

```javascript
function Student(name, age) {
  this.name = name;
  this.age = age;
}

Student.prototype.introduce = function() {
  console.log("My name is " + this.name);
};
```

---

### روش جدید (Class)

```javascript
class Student {

  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  introduce() {
    console.log("My name is " + this.name);
  }

}
```

✅ کد خواناتر است  
✅ ساختار شبیه OOP کلاسیک است  
✅ مدیریت ساده‌تر

---

# 5️⃣ تفاوت‌های مهم Class و Function

### 1️⃣ Hoisting

در جاوااسکریپت **hoisting** به این معناست که مفسر JavaScript در زمان اجرا، **تعاریف** متغیرها و توابع را قبل از اجرای خط‌به‌خط کد، به بالای محدودهٔ خود _منتقل_ می‌کند (در واقع _ظاهراً_ منتقل می‌کند، اما در عمل فقط مرحلهٔ تخصیص حافظه قبل از اجرا انجام می‌شود).

به زبان ساده:

جاوااسکریپت قبل از اجرای برنامه، متغیرها و توابع را **می‌شناسد**، حتی اگر بعد از جایی که استفاده شده‌اند تعریف شده باشند.

Function:

```javascript
const u = new User("Ali");

function User(name){
  this.name = name;
}
```

✅ کار می‌کند.

اما Class:

```javascript
const u = new User("Ali");

class User {
  constructor(name){
    this.name = name;
  }
}
```

❌ Error

چون **class hoist نمی‌شود مثل function**

---

### 2️⃣ اجبار استفاده از `new`

Constructor Function:

```javascript
User("Ali")
```

ممکن است اجرا شود (باگ ایجاد کند)

اما Class:

```javascript
User("Ali")
```

❌ Error

باید:

```javascript
new User("Ali")
```

---

### 3️⃣ Strict Mode

کلاس‌ها **به طور پیش‌فرض در strict mode اجرا می‌شوند**.

---

# 6️⃣ Transpile شدن Class

مرورگرهای قدیمی ES6 را پشتیبانی نمی‌کردند.

برای همین ابزارهایی مثل:

- Babel
- TypeScript

کد **class** را تبدیل می‌کنند به **Constructor Function + Prototype**.

مثال:

کد اصلی:

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  sayHello() {
    console.log("Hello " + this.name);
  }
}
```

بعد از transpile تقریباً می‌شود:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function () {
  console.log("Hello " + this.name);
};
```

پس:

> class فقط یک syntax جدید روی prototype system جاوااسکریپت است.

---

# ✅ جمع‌بندی

Class در ES6:

- ساختار جدید برای OOP در JavaScript
- دارای `constructor`
- دارای `method`
- استفاده از `new`
- در پشت صحنه تبدیل می‌شود به **prototype + constructor function**

---

#  سوالات 

### 1️⃣ متد `constructor` چه زمانی اجرا می‌شود؟

A) هنگام تعریف کلاس  
B) هنگام ساخت instance با `new` ✅  
C) هنگام اجرای متد  
D) هنگام import

---

### 2️⃣ متدهای داخل class در کجا ذخیره می‌شوند؟

A) داخل object  
B) داخل prototype ✅  
C) داخل constructor  
D) داخل global

---

### 3️⃣ کدام درست است؟

A) class یک سیستم جدید کاملاً متفاوت است  
B) class فقط syntax جدید روی prototype است ✅  
C) class فقط در Node.js کار می‌کند  
D) class بدون new کار می‌کند

---

### 4️⃣ کدام کد خطا می‌دهد؟

```javascript
class User {
  constructor(name){
    this.name = name;
  }
}
```

A)
```
new User("Ali")
```

B)
```
User("Ali")
```

✅ پاسخ: **B**

---

### 5️⃣ ابزار تبدیل ES6 به ES5 چیست؟

A) React  
B) Babel ✅  
C) Node  
D) npm
