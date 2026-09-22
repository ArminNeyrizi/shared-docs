در جاوااسکریپت (به‌خصوص در **ES6 کلاس‌ها**) مفهوم **Inheritance (ارث‌بری)** برای این استفاده می‌شود که یک کلاس بتواند ویژگی‌ها و متدهای کلاس دیگر را به ارث ببرد و دوباره استفاده کند.

---

# 1. `extends`
کلمه کلیدی `extends` برای ساختن یک کلاس جدید بر اساس یک کلاس دیگر استفاده می‌شود.

کلاس جدید را **subclass / child** می‌گویند و کلاس پایه را **parent / base class**.

### مثال

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(this.name + " makes a noise.");
  }
}

class Dog extends Animal {
  bark() {
    console.log(this.name + " barks.");
  }
}

const d = new Dog("Rex");
d.speak(); // Rex makes a noise.
d.bark();  // Rex barks.
```

در اینجا:

- `Dog` از `Animal` ارث‌بری می‌کند
- متد `speak()` بدون تعریف مجدد در `Dog` قابل استفاده است.

---

# 2. `super`
کلمه کلیدی `super` برای دسترسی به **کلاس والد** استفاده می‌شود.

دو کاربرد اصلی دارد:

### 1️⃣ فراخوانی constructor والد

وقتی کلاس فرزند constructor دارد باید اول `super()` را صدا بزند.

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // constructor والد
    this.breed = breed;
  }
}

const d = new Dog("Rex", "Labrador");
console.log(d.name);  // Rex
console.log(d.breed); // Labrador
```

---

### 2️⃣ فراخوانی متد والد

```javascript
class Animal {
  speak() {
    console.log("Animal sound");
  }
}

class Dog extends Animal {
  speak() {
    super.speak();
    console.log("Dog bark");
  }
}

const d = new Dog();
d.speak();
```

خروجی:

```
Animal sound
Dog bark
```

---

# 3. چه زمانی **نباید از Inheritance استفاده کنیم**

یک اصل مهم در طراحی نرم‌افزار:

**Composition over Inheritance**

یعنی در بسیاری از موارد **ترکیب (Composition)** بهتر از ارث‌بری است.

---

## ❌ مشکل 1: درخت ارث‌بری پیچیده

مثلاً:

```
Animal
 ├─ Mammal
 │   ├─ Dog
 │   └─ Cat
 └─ Bird
```

اگر سیستم بزرگ شود:

```
FlyingBird
SwimmingBird
WalkingBird
```

خیلی سریع پیچیده و غیرقابل مدیریت می‌شود.

---

## ❌ مشکل 2: وابستگی شدید (Tight Coupling)

کلاس فرزند شدیداً به پیاده‌سازی والد وابسته می‌شود.

اگر والد تغییر کند ممکن است تمام فرزندان خراب شوند.

---

## ❌ مشکل 3: استفاده اشتباه از رابطه "is-a"

ارث‌بری فقط زمانی درست است که رابطه **is-a** وجود داشته باشد.

مثال درست:

```
Dog is an Animal ✅
```

مثال اشتباه:

```
Car extends Engine ❌
```

در اینجا رابطه **has-a** است نه **is-a**.

---

# 4. Composition (ترکیب) — روش بهتر در بسیاری از موارد

به جای ارث‌بری، رفتارها را به صورت **قابل ترکیب** طراحی می‌کنیم.

### مثال

```javascript
const canFly = {
  fly() {
    console.log("Flying...");
  }
};

const canSwim = {
  swim() {
    console.log("Swimming...");
  }
};

class Duck {}

Object.assign(Duck.prototype, canFly, canSwim);

const d = new Duck();
d.fly();
d.swim();
```

در اینجا:

- رفتارها جدا هستند
- قابل ترکیب هستند
- وابستگی کمتر است

---

# خلاصه

**extends**
- برای ارث‌بری از یک کلاس استفاده می‌شود

**super**
- فراخوانی constructor یا متدهای کلاس والد

**Inheritance مناسب است وقتی**
- رابطه **is-a** وجود دارد
- ساختار ساده است

**Inheritance مناسب نیست وقتی**
- سلسله مراتب پیچیده می‌شود
- رفتارها قابل ترکیب هستند
- وابستگی زیاد ایجاد می‌شود

در این موارد **Composition بهتر است**.
