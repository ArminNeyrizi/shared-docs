
## (قبل از معرفی `class` در ES6)

قبل از ES6، جاوااسکریپت **کلاس به معنای کلاسیک** نداشت.  
اما با استفاده از چیزی به نام **Constructor Function** می‌توانستیم **شیء بسازیم**؛ دقیقاً کاری که کلاس‌ها امروز انجام می‌دهند.

---

##  مسئله‌ای که Constructor Function حل می‌کند

فرض کن می‌خواهیم اطلاعات چند دانش‌آموز را نگه داریم:

```js
const student1 = {
  name: "Ali",
  age: 20
};

const student2 = {
  name: "Sara",
  age: 22
};
```

❌ مشکل:
- تکرار کد
- سختی مدیریت
- مقیاس‌پذیر نیست

✅ راه‌حل قدیمی (قبل از ES6):  
**Constructor Function**

---

##  Constructor Function چیست؟

✅ یک **تابع معمولی** است  
✅ ولی با `new` صدا زده می‌شود  
✅ برای ساخت **Object (شیء)** استفاده می‌شود

قاعده‌ی مهم:
> اسم Constructor Function را با **حرف بزرگ** می‌نویسیم (قرارداد)

---

##  اولین Constructor Function

```js
function Student(name, age) {
  this.name = name;
  this.age = age;
}
```

📌 نکات مهم:
- `this` اشاره می‌کند به **شیء جدیدی که ساخته می‌شود**
- این تابع خودش چیزی return نمی‌کند

---

##  مفهوم `new`

وقتی می‌نویسیم:

```js
const s1 = new Student("Ali", 20);
```

جاوااسکریپت این مراحل را انجام می‌دهد:

1. یک شیء خالی می‌سازد → `{}`  
2. `this` را به آن شیء وصل می‌کند  
3. کدهای داخل تابع را اجرا می‌کند  
4. آن شیء را **برمی‌گرداند (return می‌کند)**

---

##  مفهوم Instance (نمونه)

✅ هر شیئی که با `new` ساخته شود، یک **Instance** است.

```js
const s1 = new Student("Ali", 20);
const s2 = new Student("Sara", 22);
```

- `s1` یک Instance از `Student`
- `s2` یک Instance دیگر از `Student`

✅ هر کدام:
- داده‌های جداگانه دارند
- ولی از یک الگو ساخته شده‌اند

---

##  بررسی Instance با `instanceof`

```js
console.log(s1 instanceof Student); // true
console.log(s1 instanceof Object);  // true
```

---

##  اگر `new` را فراموش کنیم چه می‌شود؟

```js
const s3 = Student("Reza", 25);
```

❌ نتیجه:
- `this` به `window` (یا `undefined` در strict mode) اشاره می‌کند
- باگ خطرناک!

✅ پس همیشه:
```js
new Student(...)
```

---

##  مقایسه با class در ES6 (فقط در حد آشنایی)

```js
class Student {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
```

📌 این فقط **ظاهر جدید** همان Constructor Function قدیمی است.

---

#  جمع‌بندی 

- Constructor Function قبل از ES6 راه ساخت Object بود
- با `new` صدا زده می‌شود
- `this` به شیء جدید اشاره می‌کند
- هر شیء ساخته‌شده یک **Instance** است

---

#  سوالات 

### Constructor Function چیست؟
A) تابعی که فقط عدد برمی‌گرداند  
B) تابعی برای ساخت چند شیء مشابه ✅  
C) نوع جدیدی از متغیر  
D) فقط در ES6 وجود دارد  

---

###  نقش `new` چیست؟
A) اجرای سریع‌تر تابع  
B) جلوگیری از خطا  
C) ساخت یک شیء جدید و اتصال آن به `this` ✅  
D) حذف prototype  

---

### خروجی کد زیر چیست؟

```js
function Car(model) {
  this.model = model;
}

const c1 = new Car("BMW");
console.log(c1.model);
```

A) undefined  
B) Car  
C) BMW ✅  
D) error  

---

###  کدام گزینه یک Instance است؟

```js
function User(name) {
  this.name = name;
}
```

A) User  
B) function User  
C) new User("Ali") ✅  
D) this  

---

###  اگر `new` را استفاده نکنیم چه اتفاقی می‌افتد؟
A) شیء ساخته نمی‌شود  
B) خطای سینتکس  
C) `this` به جای اشتباه اشاره می‌کند ✅  
D) هیچ فرقی ندارد  

