### ۱. ساختار Object Literal: ساده و صریح
رایج‌ترین و ساده‌ترین راه برای ایجاد یک شیء در جاوااسکریپت، استفاده از روش **Object Literal** است. در این روش، ما با استفاده از دو علامت آکولاد `{}`، فضایی را ایجاد می‌کنیم که مجموعه‌ای از "کلید-مقدار" (Key-Value pairs) را در خود جای می‌دهد.

```javascript
const user = {
    firstName: "سهراب",
    lastName: "سپهری",
    age: 28,
    isDeveloper: true
};
```
در مثال بالا، `user` یک شیء است که ویژگی‌های مختلف یک فرد را در یک واحدِ منسجم بسته‌بندی کرده است.

---

### ۲. ویژگی (Property) و متد (Method)
یک شیء از دو بخش اساسی تشکیل شده است:

*   **ویژگی (Property):** متغیرهایی که درون یک شیء تعریف می‌شوند و بیانگر "ویژگی‌های" آن هستند (مانند نام یا سن).
*   **متد (Method):** توابعی که درون یک شیء تعریف می‌شوند و بیانگر "رفتارها" یا کارهایی هستند که آن شیء می‌تواند انجام دهد.

بیایید شیء قبلی را با اضافه کردن یک متد، هوشمندتر کنیم:

```javascript
const laptop = {
    brand: "Apple",
    model: "MacBook Pro",
    // این یک Property است
    start: function() {
        // این یک Method است
        console.log("لپ‌تاپ روشن شد...");
    }
};

laptop.start(); // خروجی: لپ‌تاپ روشن شد...
```

---

### ۳. دسترسی به داده‌ها: نقطه یا براکت؟
برای دسترسی به مقادیر داخل یک شیء، دو راه اصلی داریم:

1.  **Dot Notation (نقطه):** رایج‌ترین روش است. `user.firstName`
2.  **Bracket Notation (براکت):** زمانی استفاده می‌شود که نام کلید ما داینامیک است یا حاوی کاراکترهای غیرمجاز (مثل فاصله) باشد. `user["firstName"]`

---

### ۴. جادوی کلمه کلیدی `this` و مفهوم زمینه (Context)
یکی از مفاهیمی که بسیاری از برنامه‌نویسان تازه کار را به چالش می‌کشد، کلمه کلیدی `this` است. در زبان ساده، `this` به **صاحب فعلی** کدی که در حال اجراست اشاره می‌کند.

وقتی درون یک متد از `this` استفاده می‌کنیم، منظورمان "همین شیئی است که متد در آن قرار دارد".

```javascript
const robot = {
    name: "آریا",
    batteryLevel: 90,
    reportStatus: function() {
        // این یعنی: نامِ همین شیء و سطح باتریِ همین شیء
        console.log(`من ${this.name} هستم و شارژ من ${this.batteryLevel}% است.`);
    }
};

robot.reportStatus(); 
// خروجی: من آریا هستم و شارژ من 90% است.
```

**چرا `this` مهم است؟**
تصور کنید اگر `this` نبود، مجبور بودید نام متغیر شیء را مستقیماً داخل متد بنویسید (`robot.name`). اما اگر نام شیء تغییر کند یا بخواهید از این متد برای چندین شیء مشابه استفاده کنید، کد شما می‌شکند. `this` باعث می‌شود متدها انعطاف‌پذیر باشند و همیشه به "زمینه" (Context) درست اشاره کنند.

> **نکته کلیدی نویسنده:** دقت کنید که رفتار `this` در توابع معمولی (Regular Functions) با توابع پیکانی (Arrow Functions) متفاوت است. در توابع پیکانی، `this` به شیءِ والدِ خود متصل نمی‌شود، بلکه از محیط اطرافش ارث‌بری می‌کند. (در فصول پیشرفته‌تر به این موضوع خواهیم پرداخت).

---
بیایید این مفاهیم را خیلی ساده و قدم‌به‌قدم ببینیم. همه‌ی مثال‌ها با یک سناریوی ساده جلو می‌روند.

---

### 1️⃣ Class Inheritance (ارث‌بری با `extends`)

ارث‌بری یعنی یک کلاس بتواند **ویژگی‌ها و متدهای کلاس دیگر را بگیرد**.

مثال:  
یک کلاس عمومی داریم به نام `Person` و یک کلاس خاص‌تر به نام `Student`.

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log("Hello, my name is " + this.name);
  }
}
```

حالا یک کلاس `Student` می‌سازیم که از `Person` ارث می‌برد:

```javascript
class Student extends Person {

}
```

الان `Student` به طور خودکار دارد:

- `name`
- `age`
- `sayHello()`

استفاده:

```javascript
const s1 = new Student("Ali", 20);

s1.sayHello();
```

خروجی:

```
Hello, my name is Ali
```

پس:

> `extends` یعنی یک کلاس از کلاس دیگر **ارث‌بری کند**.

---

### 2️⃣ super

وقتی کلاس فرزند (`Student`) **constructor خودش را داشته باشد** باید از `super` استفاده کند.

مثال:

```javascript
class Student extends Person {

  constructor(name, age, major) {
    super(name, age);
    this.major = major;
  }

}
```

ساخت نمونه:

```javascript
const s1 = new Student("Ali", 20, "Computer Science");
```

اینجا چه اتفاقی می‌افتد؟

```
super(name, age)
```

در واقع این را صدا می‌زند:

```
Person constructor
```

پس:

> `super` یعنی اجرای constructor کلاس والد.

نکته مهم:

قبل از استفاده از `this` باید `super` را صدا بزنیم.

❌ این اشتباه است:

```javascript
constructor(name, age, major) {
  this.major = major;
  super(name, age);
}
```

---

### 3️⃣ Static Method

متدهای معمولی روی **instance** اجرا می‌شوند.

مثال:

```javascript
class User {
  sayHi() {
    console.log("Hi");
  }
}

const u = new User();
u.sayHi();
```

اما **static method** روی خود کلاس اجرا می‌شود، نه روی instance.

مثال:

```javascript
class MathHelper {

  static add(a, b) {
    return a + b;
  }

}
```

استفاده:

```javascript
MathHelper.add(2,3)
```

خروجی:

```
5
```

❌ این اشتباه است:

```javascript
const m = new MathHelper();
m.add(2,3)
```

پس:

| نوع متد | اجرا روی |
|---|---|
| normal method | instance |
| static method | class |

نمونه واقعی در JS:

```
Math.random()
Array.isArray()
Object.keys()
```

این‌ها **static method** هستند.

---

### 4️⃣ Private Field

گاهی نمی‌خواهیم یک property از بیرون قابل دسترسی باشد.

ES2022 چیزی به نام **private field** معرفی کرد.

با `#` تعریف می‌شود.

مثال:

```javascript
class BankAccount {

  #balance = 0;

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }

}
```

استفاده:

```javascript
const acc = new BankAccount();

acc.deposit(100);

console.log(acc.getBalance());
```

خروجی:

```
100
```

اما:

```javascript
acc.#balance
```

❌ Error

پس:

> `#property` یعنی فقط داخل کلاس قابل دسترسی است.

---

### 5️⃣ Prototype Chain

این یکی از مهم‌ترین مفاهیم جاوااسکریپت است.

در JS وقتی به یک property دسترسی پیدا می‌کنیم:

جاوااسکریپت اول داخل خود object نگاه می‌کند.

اگر نبود:

می‌رود سراغ **prototype**

اگر آنجا هم نبود:

می‌رود سراغ **prototype بعدی**

این مسیر را می‌گویند:

> Prototype Chain

مثال:

```javascript
class Animal {
  speak() {
    console.log("Animal sound");
  }
}

class Dog extends Animal {
}
```

ساخت object:

```javascript
const d = new Dog();
```

اگر بنویسیم:

```javascript
d.speak()
```

جاوااسکریپت این مسیر را طی می‌کند:

```
d
↓
Dog.prototype
↓
Animal.prototype
↓
Object.prototype
```

و در `Animal.prototype` متد `speak` را پیدا می‌کند.

---

نمای ساده:

```
d
↓
Dog.prototype
↓
Animal.prototype
↓
Object.prototype
↓
null
```

به این زنجیره می‌گوییم:

> Prototype Chain

---

###  جمع‌بندی 

**extends**
- ارث‌بری از کلاس دیگر

**super**
- صدا زدن constructor کلاس والد

**static**
- متد متعلق به کلاس نه instance

**private field (#)**
- property خصوصی

**prototype chain**
- مسیر جستجوی property در JS

---

### خلاصه کلی
در این بخش آموختیم که اشیا، کپسول‌هایی برای نگهداری داده‌ها (Properties) و رفتارها (Methods) هستند. استفاده از `this` به ما اجازه می‌دهد تا درون یک شیء، به سایر اجزای همان شیء دسترسی داشته باشیم و کدی پویا بنویسیم. در فصل بعدی، به سراغ آرایه‌ها خواهیم رفت تا ببینیم چگونه می‌توان لیستی از این اشیا را مدیریت کرد.
