
## 1) this در جاوااسکریپت (خلاصهٔ ذهنی)
در جاوااسکریپت، مقدار **this** به **نحوهٔ صدا زدن تابع** بستگی دارد، نه محل تعریف آن.  
استثنا: **arrow function** که this خودش را **از محیط بیرونی (lexical scope)** به ارث می‌گیرد.

-----------------------------------

## 2) this در متدهای کلاس یا شی (Object / Class Methods)

### الف) در متدهای یک object literal
وقتی تابع به عنوان **متد یک شی** فراخوانی شود، این یعنی:
```js
const obj = {
  x: 10,
  say() {
    console.log(this.x)
  }
}

obj.say()  // this === obj → خروجی: 10
```

در اینجا this برابر **شی‌ای است که قبل از نقطه قرار دارد**.

---

### ب) در کلاس‌ها (class methods)
در کلاس‌ها هم همین قانون برقرار است؛ متد در زمان فراخوانی تعیین می‌کند this چیست.

```js
class Person {
  constructor(name) {
    this.name = name
  }
  say() {
    console.log(this.name)
  }
}

const p = new Person("Ali")
p.say()  // this === p → "Ali"
```

---

### نکته مهم: جدا کردن متد از شی
اگر متد را به یک متغیر جدا منتقل کنیم، this از دست می‌رود:

```js
const m = p.say
m()   // this === undefined (در strict mode)
```

در strict mode this = undefined  
در non-strict اسکوپ global را اشاره می‌کند (window در مرورگر).

-----------------------------------

## 3) this در Arrow Function

### قانون اصلی
Arrow function **this ندارد**.  
this را از محیط بیرونی **lexically inherit** می‌کند.

مثال:

```js
const obj = {
  x: 10,
  say: () => {
    console.log(this.x)
  }
}

obj.say()  // this از obj نیست → this از محیط بیرونی است
```

نتیجه معمولاً undefined یا چیزی غیرمنتظره است، چون arrow function به obj bind نمی‌شود.

---

### کاربرد معمول arrow function

#### داخل متدها برای حفظ this بیرونی
```js
function Person(){
  this.age = 0

  setInterval(() => {
    this.age++
    console.log(this.age)
  }, 1000)
}
```

اگر از تابع معمولی استفاده می‌کردیم، this داخل setInterval به window اشاره می‌کرد.

-----------------------------------

## 4) اشتباهات رایج و نکات کلیدی

### 1) اشتباه در استفاده از arrow function به‌عنوان متد شی
خیلی‌ها اشتباهاً از arrow function در متدهای object استفاده می‌کنند:

```js
const obj = {
  x: 10,
  say: () => console.log(this.x)
}
```

این اشتباه است چون this ربطی به obj ندارد.

---

### 2) گم شدن this هنگام callback

```js
class Person {
  constructor(name){
    this.name = name
  }
  sayAsync(){
    setTimeout(function(){
      console.log(this.name)  // undefined
    }, 1000)
  }
}
```

حل:  
- arrow function  
- bind  
- یا متغیر ذخیره this مثل self = this (قدیمی)

---

### 3) call / apply / bind

#### call: اجرای تابع با this سفارشی + آرگومان‌ها جدا
```js
func.call(obj, a, b)
```

#### apply: همین، ولی آرگومان‌ها آرایه است
```js
func.apply(obj, [a, b])
```

#### bind: ساخت یک تابع جدید با this ثابت
```js
const f = func.bind(obj)
f()
```

---

### مثال کاربردی
```js
function greet(){
  console.log("Hi " + this.name)
}

const user = { name: "Sara" }

greet.call(user)  // Hi Sara
```

---

### 4) اشتباه بزرگ: فکر کنیم this به lexical scope مربوط است
this در تابع معمولی **lexical نیست**. فقط در arrow function چنین است.

```js
function f(){
  console.log(this)
}
```

this در زمان اجرا تعیین می‌شود، نه تعریف.

-----------------------------------

## 5) جمع‌بندی سریع

- this تعیین می‌شود توسط **نحوه‌ی فراخوانی تابع**
- در متدهای شی و کلاس: this = شی‌ای که متد را صدا زده
- در arrow function: this = محیط بیرونی (lexical)
- call/apply/bind برای کنترل دستی this
- اشتباه رایج: استفاده از arrow function به‌عنوان متد شی

در اینجا ۵ سؤال چهارگزینه‌ای مفهومی و کاربردی از مباحث **this** طراحی کرده‌ام تا میزان تسلط خود را بسنجید. پاسخ‌نامه به همراه تحلیل در انتهای سؤالات قرار دارد.

---

### سؤال ۱: خروجی کد زیر چیست؟ (فرض کنید در حالت Strict Mode هستیم)

```javascript
const user = {
  name: "Arash",
  greet() {
    console.log(this.name);
  }
};

const say = user.greet;
say();
```

الف) `Arash`  
ب) `undefined`  
ج) `TypeError: Cannot read property 'name' of undefined`  
د) `Window` (یا شی Global)

---

### سؤال ۲: خروجی قطعه کد زیر چیست؟

```javascript
const counter = {
  count: 10,
  increment: () => {
    this.count++;
    console.log(this.count);
  }
};

counter.increment();
```

الف) `11`  
ب) `10`  
ج) `undefined`  
د) `NaN` (چون `undefined ++` می‌شود NaN)

---

### سؤال ۳: تفاوت اصلی متد `bind` با متدهای `call` و `apply` در چیست؟

الف) `bind` تابع را بلافاصله اجرا نمی‌کند، بلکه یک تابع جدید برمی‌گرداند.  
ب) `bind` فقط برای Arrow Functionها کاربرد دارد.  
ج) `bind` برخلاف بقیه نمی‌تواند آرگومان ورودی بگیرد.  
د) تفاوتی ندارند و هر سه تابع را بلافاصله با `this` مشخص اجرا می‌کنند.

---

### سؤال ۴: در کد زیر، چرا داخل `setTimeout` از Arrow Function استفاده شده است؟

```javascript
class Timer {
  constructor() {
    this.seconds = 0;
  }
  start() {
    setTimeout(() => {
      this.seconds++;
      console.log(this.seconds);
    }, 1000);
  }
}

const myTimer = new Timer();
myTimer.start();
```

الف) چون Arrow Functionها سریع‌تر اجرا می‌شوند.  
ب) برای اینکه `this` به شیء ساخته شده از کلاس `Timer` اشاره کند (ارث‌بری لکسیکال).  
ج) چون در `setTimeout` نمی‌توان از تابع معمولی (`function`) استفاده کرد.  
د) چون تابع `start` خودش یک متد است.

---

### سؤال ۵: اگر بخواهیم تابع زیر را طوری اجرا کنیم که `this` به شیء `person` اشاره کند و خروجی `25` باشد، کدام گزینه صحیح است؟

```javascript
function getAge(bonus) {
  return this.age + bonus;
}

const person = { age: 20 };
```

الف) `getAge.call(person, 5)`  
ب) `getAge.apply(person, [5])`  
ج) `getAge.bind(person)(5)`  
د) هر سه مورد درست هستند.

---

### پاسخ‌نامه و تحلیل:

1.  **گزینه ج (`TypeError`)**: وقتی متد را در یک متغیر (`say`) می‌ریزید، ارتباط آن با شیء `user` قطع می‌شود. در Strict Mode، وقتی تابعی به صورت ساده فراخوانی شود، `this` برابر `undefined` است و تلاش برای دسترسی به `undefined.name` باعث خطا می‌شود.
2.  **گزینه د (`NaN`)**: چون `increment` یک **Arrow Function** است، `this` را از اسکوپ بیرونی (که اینجا Global/Window است) می‌گیرد. در اسکوپ Global متغیری به نام `count` وجود ندارد (`undefined`) و عملیات ریاضی روی آن مقدار `NaN` تولید می‌کند.
3.  **گزینه الف**: این تفاوت بنیادی است. `call` و `apply` تابع را "همین الان" اجرا می‌کنند، اما `bind` یک نسخه کپی از تابع می‌سازد که `this` آن "قفل" شده است تا بعداً استفاده شود.
4.  **گزینه ب**: اگر از تابع معمولی استفاده می‌شد، `this` داخل `setTimeout` به Global یا `undefined` اشاره می‌کرد. Arrow function باعث می‌شود `this` همان مقداری باشد که در متد `start` وجود دارد (یعنی نمونه ساخته شده از کلاس).
5.  **گزینه د**: هر سه روش برای تغییر `this` صحیح هستند. `call` آرگومان را مستقیم می‌گیرد، `apply` در آرایه می‌گیرد، و `bind` تابعی برمی‌گرداند که می‌توان بلافاصله آن را با آرگومان صدا زد.

