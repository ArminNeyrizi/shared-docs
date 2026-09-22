## بخش ۲: مفاهیم Async / Await

مدت زمان پیشنهادی مطالعه: **۲ تا ۳ ساعت**

---

## مقدمه

یکی از مهم‌ترین تفاوت‌های برنامه‌نویسی در Node.js با بسیاری از زبان‌ها، **غیرهمزمان (Asynchronous)** بودن آن است.  
Node.js برای مدیریت هم‌زمان هزاران درخواست طراحی شده و این کار بدون درک درست از async/await تقریباً غیرممکن است.

در این بخش:
- مفهوم غیرهمزمانی را می‌فهمیم
- مشکل Callback Hell را بررسی می‌کنیم
- Promise را مرور می‌کنیم
- و در نهایت به async/await می‌رسیم

---

## ۱. اجرای همزمان در JavaScript یعنی چه؟

جاوااسکریپت **Single Thread** است؛ یعنی در هر لحظه فقط یک کار اجرا می‌شود.  
اما با کمک **Event Loop** می‌تواند کارهای زمان‌بر (مثل خواندن فایل یا درخواست شبکه) را به صورت غیرهمزمان مدیریت کند.

مثال ساده:

```js
console.log("شروع")

setTimeout(() => {
  console.log("وسط")
}, 1000)

console.log("پایان")
```

خروجی:

```
شروع
پایان
وسط
```

✅ کد متوقف نمی‌شود و به کار خود ادامه می‌دهد.

---

## ۲. مشکل کدهای همزمان (Blocking Code)

اگر کدی زمان‌بر باشد و به صورت همزمان اجرا شود، کل برنامه قفل می‌شود.

مثال بد:

```js
const data = fs.readFileSync("file.txt")
console.log(data)
```

در Node.js ترجیح می‌دهیم همیشه از نسخه‌های غیرهمزمان استفاده کنیم.

---

## ۳. Callback چیست؟

Callback یعنی **تابعی که به تابع دیگر داده می‌شود** تا بعداً اجرا شود.

مثال:

```js
function getData(callback) {
  setTimeout(() => {
    callback("data loaded")
  }, 1000)
}

getData((result) => {
  console.log(result)
})
```

✅ مزیت: ساده و سریع  
❌ مشکل: تو در تو شدن کد

---

## ۴. Callback Hell (جهنم کال‌بک)

وقتی چند عملیات وابسته به هم داشته باشیم:

```js
login(user, () => {
  getProfile(() => {
    getPosts(() => {
      getComments(() => {
        // 😵
      })
    })
  })
})
```

این ساختار:
- خوانایی پایین
- نگهداری سخت
- مدیریت خطا دشوار

---

## ۵. Promise چیست؟

Promise راه‌حل استاندارد برای حل مشکل Callback Hell است.

Promise سه حالت دارد:
- pending
- fulfilled
- rejected

مثال:

```js
const getData = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("data loaded")
    }, 1000)
  })
}
```

استفاده:

```js
getData()
  .then(data => console.log(data))
  .catch(err => console.error(err))
```

---

## ۶. زنجیره Promise‌ها (Promise Chaining)

```js
getUser()
  .then(user => getPosts(user.id))
  .then(posts => getComments(posts[0].id))
  .then(comments => console.log(comments))
  .catch(err => console.error(err))
```

✅ بهتر از Callback Hell  
❌ هنوز کمی پیچیده و طولانی

---

## ۷. Async / Await چیست؟

`async/await` سینتکس مدرن برای کار با Promise‌ها است که کد را **شبیه کد همزمان** می‌کند.

```js
async function main() {
  const data = await getData()
  console.log(data)
}

main()
```

🔹 `async` → تابع همیشه Promise برمی‌گرداند  
🔹 `await` → منتظر resolve شدن Promise می‌ماند

---

## ۸. مدیریت خطا با try / catch

در async/await، خطاها با `try/catch` مدیریت می‌شوند.

```js
async function load() {
  try {
    const data = await getData()
    console.log(data)
  } catch (error) {
    console.error("خطا:", error)
  }
}
```

✅ خوانا  
✅ مشابه زبان‌های دیگر

---

## ۹. اجرای موازی Promise‌ها

برای اجرای همزمان چند Promise:

```js
const [users, posts] = await Promise.all([
  getUsers(),
  getPosts()
])
```

⚠️ اگر یکی fail شود، همه fail می‌شوند.

---

## ۱۰. Async / Await در Node.js واقعی

مثال خواندن فایل:

```js
import { readFile } from "fs/promises"

async function read() {
  const data = await readFile("file.txt", "utf-8")
  console.log(data)
}

read()
```

این الگو در:
- دیتابیس
- API
- فایل‌ها
- شبکه

مدام استفاده می‌شود.

---

## 🔍 خلاصه این بخش

در این بخش یاد گرفتیم:

✅ مفهوم غیرهمزمانی  
✅ Callback و مشکلات آن  
✅ Promise و Promise chaining  
✅ async / await  
✅ مدیریت خطا با try/catch  
✅ اجرای موازی Promise‌ها  

---

## 💻 تمرین‌ها

1️⃣ تابع async بنویس که بعد از ۲ ثانیه یک متن برگرداند.  
2️⃣ دو Promise بساز و با `Promise.all` آن‌ها را اجرا کن.  
3️⃣ یک تابع async بنویس که خطا تولید کند و آن را با try/catch مدیریت کند.  
4️⃣ یک فایل متنی را به صورت async بخوان و در کنسول چاپ کن.

---
