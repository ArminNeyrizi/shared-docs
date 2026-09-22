
# فصل ۱: پیش‌نیازها  
## بخش ۱: آشنایی با JavaScript (ES6+)

مدت زمان پیشنهادی مطالعه: **۲ تا ۳ ساعت**

---

## مقدمه

پیش از ورود به دنیای Node.js، باید زبان جاوااسکریپت را در سطحی فراتر از استفاده در مرورگر بشناسیم.  
Node.js بر پایه همین زبان ساخته شده است، اما در محیط **سرور** اجرا می‌شود؛ به همین دلیل درک درست از مفاهیم جدید **ES6 و بعد از آن (ES2015+)** بسیار حیاتی است.

در این بخش، مروری خواهیم داشت بر ویژگی‌های کلیدی جاوااسکریپت مدرن که در محیط‌های Node.js به‌صورت روزمره استفاده می‌شوند.

---

## ۱. متغیرها با let و const

در نسخه‌های قدیمی جاوااسکریپت از `var` برای تعریف متغیر استفاده می‌شد.  
اما در استاندارد **ES6** دو کلمه کلیدی جدید معرفی شد: `let` و `const`.

- `let`: برای تعریف متغیرهایی که احتمال تغییر مقدار دارند.  
- `const`: برای تعریف متغیرهایی که مقدارشان نباید تغییر کند.

مثال:

```js
let counter = 1
counter++ // مجاز

const PI = 3.1416
PI = 3 // خطا، مقدار ثابت است
```

**تفاوت کلیدی:**  
- `var` به صورت **function-scoped** عمل می‌کند (محدوده تابع).
- `let` و `const` به صورت **block-scoped** هستند (محدوده `{}`).

---

## ۲. توابع پیکان‌دار (Arrow Functions)

تابع‌های پیکان‌دار، نسخه کوتاه‌تر و مدرن‌تر برای نوشتن تابع هستند.

```js
const add = (a, b) => a + b
```

ویژگی مهم آن‌ها این است که:
- عملگر `this` را از محیط بالاتر به ارث می‌برند (برخلاف `function` معمولی).

مثال تفاوت:

```js
function normal() {
  console.log(this)
}

const arrow = () => {
  console.log(this)
}
```

در Node.js، رفتار `this` در توابع پیکان‌دار برای کار با کال‌بک‌ها (callback) و کلاس‌ها اهمیت دارد.

---

## ۳. Template Literals

در ES6 می‌توان رشته‌ها را راحت‌تر و خواناتر ساخت:
```js
const name = "Ali"
console.log(`سلام ${name}! خوش آمدی به Node.js`)
```

ویژگی‌ها:
- پشتیبانی از چند خطی (multi-line)
- درج متغیر با `${}`

---

## ۴. Destructuring (تجزیه‌سازی)

به شما امکان می‌دهد خاصیت‌های یک شیء یا آرایه را به‌سادگی استخراج کنید.

مثال با شیء:

```js
const user = { name: "Sara", age: 25 }
const { name, age } = user
console.log(name, age) // Sara 25
```

مثال با آرایه:
```js
const nums = [10, 20, 30]
const [a, b] = nums
console.log(a, b) // 10 20
```

در Node.js این ویژگی را زیاد در خواندن تنظیمات، پاسخ‌های API و فایل‌های JSON می‌بینیم.

---

## ۵. Spread و Rest Operator

### Spread
برای **گسترش (spread)** عناصر:
```js
const arr1 = [1, 2]
const arr2 = [...arr1, 3, 4]
console.log(arr2) // [1, 2, 3, 4]
```

### Rest
برای **دریافت بقیه‌ عناصر**:
```js
function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0)
}
console.log(sum(1, 2, 3)) // 6
```

---

## ۶. کلاس‌ها (Classes)

در ES6، کلاس‌ها اضافه شدند تا ساختارهای داده و رفتارها را بهتر مدل کنیم.

مثال:
```js
class User {
  constructor(name) {
    this.name = name
  }

  greet() {
    console.log(`سلام ${this.name}`)
  }
}

const user1 = new User("Nima")
user1.greet()
```

کلاس‌ها در Node.js برای ساخت **مدل‌ها (Models)، سرویس‌ها (Services)** و **ماژول‌های برنامه** کاربرد دارند.

---

## ۷. ماژول‌ها (Modules)

Node.js از دو سیستم ماژول پشتیبانی می‌کند:
- **CommonJS** (`require`, `module.exports`)
- **ES Modules** (`import`, `export`)

مثال CommonJS:
```js
const fs = require("fs")
```

مثال ES Module:
```js
import fs from "fs"
```

در پروژه‌های جدید Node.js معمولاً از **ES Modules** استفاده می‌شود.

---

## ۸. Promise و Async/Await (پیش‌مقدمه)

یکی از مهم‌ترین تغییرات ES6، ظهور Promise‌ها است:

```js
function getData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("done"), 1000)
  })
}

getData().then(console.log)
```

و در ES8 با `async/await` می‌توان کد خواناتر نوشت:

```js
async function main() {
  const result = await getData()
  console.log(result)
}
main()
```

ما در فصل بعد به صورت کامل این مفاهیم را بررسی می‌کنیم.

---

## ۹. Import و Export در سطح پروژه

می‌توانیم فایل‌ها را جدا کرده و در پروژه ماژولار عمل کنیم.

main.js:

```js
import { add } from "./math.js"

console.log(add(2, 5))
```

math.js:

```js
export const add = (a, b) => a + b
```

---

## 🔍 خلاصه این بخش

در این قسمت یاد گرفتیم:

✅ تفاوت `let` و `const` با `var`  
✅ Arrow Function و رفتار `this`  
✅ Template Literals و Destructuring  
✅ Spread و Rest Operators  
✅ کلاس‌ها و ماژول‌ها  
✅ مقدمه‌ای از Promise‌ها و async/await  

این موارد پایه‌ی کار در Node.js هستند و در فصل‌های بعد دائماً استفاده می‌شوند.

---

## 💻 تمرین‌ها

1️⃣ تابعی بنویس که آرایه‌ای را گرفته و فقط اعضای بزرگتر از 10 را چاپ کند با استفاده از Arrow Function.  
2️⃣ یک کلاس بساز که نام کاربر را بگیرد و با Template Literal جمله‌ای سلام چاپ کند.  
3️⃣ با استفاده از ماژول‌ها، فایل جداگانه‌ای بساز برای محاسبه‌ی مجموع و میانگین چند عدد.  
4️⃣ از Destructuring برای استخراج نام و سن از یک شیء استفاده کن و در کنسول چاپ کن.
