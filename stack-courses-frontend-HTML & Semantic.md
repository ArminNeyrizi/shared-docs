
# 📖 سرفصل درس HTML & Semantic

## واحد: ۲ | ساعت تدریس: ۳۰ ساعت

---

## 📋 ساختار کلی

| فصل | عنوان | ساعت |
|:---:|------|:---:|
| ۱ | آشنایی با وب و HTML | ۲ |
| ۲ | ساختار اولیه سند HTML | ۳ |
| ۳ | تگ‌های پایه‌ای (متنی و عنوان) | ۴ |
| ۴ | لینک‌ها و تصاویر | ۳ |
| ۵ | لیست‌ها و جداول | ۳ |
| ۶ | فرم‌ها و ورودی‌ها | ۵ |
| ۷ | المان‌های رسانه‌ای (صدا، ویدیو، iframe) | ۳ |
| ۸ | Semantic HTML (بخش ۱) | ۳ |
| ۹ | Semantic HTML (بخش ۲) | ۳ |
| ۱۰ | SEO پایه و Accessibility | ۲ |
| **جمع** | | **۳۰** |

---

## 🔹 فصل ۱: آشنایی با وب و HTML
**ساعت: ۲**

```
☐ تاریخچه وب و اینترنت
☐ HTML چیست و چه نقشی دارد؟
☐ تفاوت HTML, CSS, JavaScript
☐ مرورگر چگونه کد HTML را می‌خواند؟
☐ آشنایی با مفهوم Tags و Elements
☐ نصب و آشنایی با ویرایشگر کد (VS Code)
☐ ساختار Client-Server به زبان ساده
```

---

## 🔹 فصل ۲: ساختار اولیه سند HTML
**ساعت: ۳**

```
☐ ساختار کامل یک سند HTML5
☐ تگ <!DOCTYPE html>
☐ تگ <html>, <head>, <body>
☐ تگ <meta charset="UTF-8">
☐ تگ <title> و اهمیت آن
☐ توضیح تگ‌های Meta (viewport, description, keywords)
☐ مفهوم Head و Body
☐ نوشتن اولین صفحه HTML
☐ قوانین نام‌گذاری و ساختار فایل‌ها
☐ نام‌گذاری فایل index.html
```

---

## 🔹 فصل ۳: تگ‌های پایه‌ای (متنی و عنوان)
**ساعت: ۴**

```
☐ تگ‌های عنوان: <h1> تا <h6>
☐ تگ پاراگراف: <p>
☐ تگ خط جدید: <br>
☐ تگ <hr> (خط افقی)
☐ تگ‌های متنی:
   - <strong> و <b>
   - <em> و <i>
   - <u> (زیرخط)
   - <s> یا <del> (خط خورده)
   - <mark> (هایلایت)
☐ تگ‌های <span> و <div> (مقدمه)
☐ تگ‌های نمایشی کد:
   - <code>
   - <pre>
   - <blockquote>
☐ HTML Entities (کاراکترهای خاص)
   - &nbsp; &lt; &gt; &amp; &copy;
☐ کامنت‌گذاری در HTML
```

---

## 🔹 فصل ۴: لینک‌ها و تصاویر
**ساعت: ۳**

```
☐ تگ <a> و خصوصیت href
☐ لینک‌های مطلق و نسبی
☐ خصوصیت target (_self, _blank)
☐ لینک‌های لنگر (Anchor Links) با id
☐ ارسال ایمیل با mailto:
☐ تگ <img> و خصوصیت‌های آن:
   - src (آدرس تصویر)
   - alt (متن جایگزین)
   - width / height
☐ تفاوت فرمت‌های تصویر (jpg, png, gif, svg, webp)
☐ لینک‌های تصویری
☐ نقشه تصویری (<map>, <area>) - مقدماتی
```

---

## 🔹 فصل ۵: لیست‌ها و جداول
**ساعت: ۳**

```
☐ لیست‌های نامرتب: <ul>, <li>
☐ لیست‌های مرتب: <ol>, <li>
☐ لیست‌های تو در تو
☐ لیست‌های تعریفی: <dl>, <dt>, <dd>
☐ تگ‌های جدول:
   - <table>, <thead>, <tbody>, <tfoot>
   - <tr>, <th>, <td>
☐ خصوصیت colspan و rowspan
☐ استایل‌دهی مقدماتی جداول
☐ مثال‌های کاربردی جدول
```

---

## 🔹 فصل ۶: فرم‌ها و ورودی‌ها
**ساعت: ۵**

```
☐ تگ <form> و خصوصیت‌های آن
   - action
   - method (GET, POST)
☐ تگ <input> و انواع آن:
   - text, password, email, number
   - tel, url, search, color, date
   - file, hidden
☐ تگ‌های مرتبط با input:
   - <label>
   - <fieldset>, <legend>
☐ تگ <textarea>
☐ تگ <select> و <option>
☐ تگ <button>
☐ تگ‌های جدید HTML5:
   - <datalist>
   - <output>
   - <progress>
   - <meter>
☐ خصوصیت‌های مهم:
   - placeholder, required, disabled, readonly
   - min, max, step, pattern
   - autocomplete
☐ اعتبارسنجی سمت کلاینت (مقدماتی)
```

---

## 🔹 فصل ۷: المان‌های رسانه‌ای
**ساعت: ۳**

```
☐ تگ <audio> و خصوصیت‌های آن:
   - src, controls, autoplay, loop, muted
   - پشتیبانی از فرمت‌های مختلف (mp3, ogg, wav)
☐ تگ <video> و خصوصیت‌های آن:
   - src, controls, autoplay, loop, muted, poster
   - preload, width, height
   - فرمت‌ها (mp4, webm, ogg)
☐ تگ <source> برای پشتیبانی چند فرمت
☐ تگ <iframe> (جاسازی صفحات)
   - جاسازی YouTube, Google Maps
   - خصوصیت sandbox (امنیت)
☐ تگ <embed> و <object>
☐ تگ <picture> و Responsive Images
☐ آشنایی با CDN و لینک‌دهی خارجی
```

---

## 🔹 فصل ۸: Semantic HTML - بخش ۱
**ساعت: ۳**

```
☐ HTML معنایی چیست و چرا مهم است؟
☐ تفاوت Semantic و Non-Semantic
☐ تگ‌های ساختاری صفحه:
   - <header>
   - <nav>
   - <main>
   - <section>
   - <article>
   - <aside>
   - <footer>
☐ ساختاردهی یک صفحه وب واقعی
☐ تحلیل ساختار صفحات معروف
☐ Rule of Seven در طراحی وب (مقدمه)
```

---

## 🔹 فصل ۹: Semantic HTML - بخش ۲
**ساعت: ۳**

```
☐ تگ‌های متنی معنایی:
   - <time>, <address>, <abbr>
   - <mark>, <details>, <summary>
   - <figure>, <figcaption>
☐ تگ‌های نرده‌ای معنایی:
   - <header>, <footer> (مقدمه و نتیجه بخش)
   - <nav>, <menu>
☐ تگ <article> در مقابل <section>
☐ الگوی ساختار: Document Outline
☐ الگوریتم عنوان‌بندی (Heading Ranking)
☐ خطاهای رایج Semantic HTML
☐ Semantic در فرم‌ها:
   - <label>, <datalist>
   - <fieldset>, <legend>
```

---

## 🔹 فصل ۱۰: SEO پایه و Accessibility
**ساعت: ۲**

```
☐ نقش HTML در سئو (SEO)
☐ تگ‌های مهم برای سئو:
   - <title>
   - <meta description>
   - Open Graph Tags (og:title, og:description)
☐ ساختار عنوان‌ها و اهمیت آن برای Google
☐ استفاده صحیح از alt در تصاویر
☐ اصول دسترس‌پذیری (a11y):
   - کنتراست رنگ
   - اندازه فونت
   - قابلیت ناوبری با کیبورد
☐ ابزارهای بررسی Accessibility:
   - WAVE, Lighthouse
☐ HTML برای Screen Readers
```

---

## 📝 پروژه‌های درس

| پروژه | توضیح |
|-------|-------|
| **پروژه ۱** | ساخت صفحه مقاله وبلاگی با تصاویر و لینک |
| **پروژه ۲** | ساخت جدول مقایسه‌ای محصول |
| **پروژه ۳** | فرم ثبت‌نام کامل با اعتبارسنجی |
| **پروژه ۴** | ساخت صفحه لندینگ با Semantic HTML |

---

## 📚 منابع پیشنهادی

| نوع | منبع |
|-----|------|
| 📖 مستندات | [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML) |
| 🎥 ویدیویی | دوره‌های رایگان freeCodeCamp |
| 🏆 تمرین | [HTML Practice على freeCodeCamp](https://www.freecodecamp.org/learn/2022/responsive-web-design/) |
| 📝 چک‌لیست | W3C Semantic HTML Checklist |

---

> **⚠️ نکته مهم:** در این درس فقط **HTML** تدریس می‌شود و از CSS/JS استفاده نمی‌شود تا تمرکز دانشجو فقط روی **ساختار و معنا** باشد.