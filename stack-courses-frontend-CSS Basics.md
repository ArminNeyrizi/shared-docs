
# 📖 سرفصل درس CSS Basics

## واحد: ۲ | ساعت تدریس: ۳۰ ساعت

---

## 📋 ساختار کلی

| فصل | عنوان | ساعت |
|:---:|------|:---:|
| ۱ | آشنایی با CSS و روش‌های اتصال | ۳ |
| ۲ | انتخابگرها (Selectors) | ۵ |
| ۳ | مدل جعبه‌ای (Box Model) | ۴ |
| ۴ | رنگ‌ها و پس‌زمینه‌ها | ۳ |
| ۵ | تایپوگرافی (متن و فونت) | ۴ |
| ۶ | آبشار و اولویت‌ها (Cascade & Specificity) | ۴ |
| ۷ | موقعیت‌دهی (Position & Layout) | ۴ |
| ۸ | شبه‌کلاس‌ها و شبه‌عناصر | ۳ |
| **جمع** | | **۳۰** |

---

## 🔹 فصل ۱: آشنایی با CSS و روش‌های اتصال
**ساعت: ۳**

```
☐ CSS چیست و چه نقشی دارد؟
☐ تاریخچه CSS (CSS1, CSS2, CSS3)
☐ تفاوت HTML و CSS در ساخت صفحه وب
☐ سه روش اتصال CSS به HTML:
   - Inline CSS (درون‌خطی)
   - Internal CSS (داخلی)
   - External CSS (خارجی)
☐ ساختار یک قانون CSS (Syntax)
   - Selector
   - Property
   - Value
☐ کامنت‌گذاری در CSS
☐ نام‌گذاری فایل style.css
☐ نصب و آشنایی با DevTools مرورگر
☐ آشنایی با پنل Elements و Styles
☐ اولین استایل‌دهی عملی
```

---

## 🔹 فصل ۲: انتخابگرها (Selectors)
**ساعت: ۵**

```
☐ انتخابگرهای پایه:
   - Element Selector (p, h1, div)
   - Class Selector (.classname)
   - ID Selector (#idname)
   - Universal Selector (*)
☐ انتخابگرهای ترکیبی:
   - Descendant Selector (space)
     مثال: div p
   - Child Selector (>)
     مثال: ul > li
   - Adjacent Sibling (+)
     مثال: h1 + p
   - General Sibling (~)
     مثال: h1 ~ p
☐ انتخابگرهای ویژگی (Attribute Selectors):
   - [attr]
   - [attr="value"]
   - [attr^="value"]  (شروع با)
   - [attr$="value"]  (پایان با)
   - [attr*="value"]  (شامل)
   - مثال کاربردی: انتخاب لینک‌های خارجی
☐ گروه‌بندی انتخابگرها (Selector List)
   مثال: h1, h2, h3 { color: red; }
☐ انتخابگرهای چندگانه (Chaining)
   مثال: h1.title.heading
☐ تفاوت Class و ID در عمل
☐ قوانین نام‌گذاری BEM (مقدماتی)
☐ نام‌گذاری با Kebab-case
☐ تمرین: انتخابگرها در حالت‌های مختلف
```

---

## 🔹 فصل ۳: مدل جعبه‌ای (Box Model)
**ساعت: ۴**

```
☐ مفهوم Box Model چیست؟
☐ چهار بخش Box Model:
   - Content (محتوا)
   - Padding (پدینگ / فاصله داخلی)
   - Border (حاشیه)
   - Margin (مارجین / فاصله خارجی)
☐ خصوصیت‌های مخفف (Shorthand):
   - padding: 10px; (چهار طرف)
   - padding: 10px 20px; (بالا/پایین - چپ/راست)
   - padding: 10px 20px 30px 40px; (ساعتگرد)
☐ تفاوت box-sizing: content-box vs border-box
   - content-box (پیش‌فرض)
   - border-box (محاسبه آسان‌تر)
☐ مثال عملی: ساخت دکمه (Button)
☐ خصوصیت‌های جداگانه:
   - padding-top, padding-right, padding-bottom, padding-left
   - margin-top, margin-right, margin-bottom, margin-left
   - border-top-width, border-style, border-color
☐ مشکل Margin Collapse
☐ ترفند: box-sizing: border-box برای همه المان‌ها
☐ تمرین: ساخت کارت محصول با Box Model
```

---

## 🔹 فصل ۴: رنگ‌ها و پس‌زمینه‌ها
**ساعت: ۳**

```
☐ روش‌های تعریف رنگ در CSS:
   - نام رنگ (red, blue, white)
   - کد هگزادسیمال (#FF0000, #F00)
   - RGB (rgb(255, 0, 0))
   - RGBA (rgba(255, 0, 0, 0.5))
   - HSL (hsl(0, 100%, 50%))
   - HSLA (hsla(0, 100%, 50%, 0.5))
☐ خصوصیت color (رنگ متن)
☐ خصوصیت background-color
☐ پس‌زمینه تصویری:
   - background-image
   - background-repeat (repeat, no-repeat, repeat-x, repeat-y)
   - background-position (center, left, right, percentages)
   - background-size (cover, contain, 100px 200px)
   - background-attachment (scroll, fixed)
☐ مخفف background
☐ گرادیان‌ها (Gradients):
   - linear-gradient
   - radial-gradient
   - جهت گرادیان (to right, to bottom, 45deg)
   - چند رنگ در گرادیان
☐ استفاده از پس‌زمینه‌های چندگانه (Multiple Backgrounds)
☐ ابزار انتخاب رنگ و پالت رنگ
☐ تمرین: ساخت هدر با گرادیان
```

---

## 🔹 فصل ۵: تایپوگرافی (متن و فونت)
**ساعت: ۴**

```
☐ خانواده فونت (font-family):
   - Generic Families: serif, sans-serif, monospace, cursive, fantasy
   - Font Stack (ترکیب فونت‌ها)
   - نام فونت‌های فارسی (Vazirmatn, Sahel)
☐ اندازه فونت (font-size):
   - واحدها: px, em, rem, %, pt
   - تفاوت em و rem
   - تنظیم اندازه با rem (رویکرد مدرن)
☐ ضخامت فونت (font-weight):
   - مقادیر عددی: 100-900
   - مقادیر کلمه‌ای: normal, bold, lighter, bolder
☐ استایل فونت (font-style):
   - normal, italic, oblique
☐ خط ارتفاع (line-height):
   - مقدار عددی (بدون واحد)
   - مقدار درصدی
   - بهترین مقدار برای متن خوانا: 1.5 تا 1.8
☐ فونت فارسی (direction, unicode-bidi)
☐ تراز متن (text-align):
   - left, right, center, justify
☐ تزئین متن (text-decoration):
   - underline, overline, line-through, none
☐ تورم متن (text-transform):
   - uppercase, lowercase, capitalize
☐ فاصله حروف (letter-spacing)
☐ فاصله کلمات (word-spacing)
☐ فاصله خطوط (line-height)
☐ تورفتگی متن (text-indent)
☐ سایه متن (text-shadow)
☐ شکستن متن (word-wrap, overflow-wrap)
☐ بارگذاری فونت سفارشی (@font-face)
☐ سرویس Google Fonts
☐ تمرین: استایل‌دهی مقاله وبلاگ
```

---

## 🔹 فصل ۶: آبشار و اولویت‌ها (Cascade & Specificity)
**ساعت: ۴**

```
☐ مفهوم آبشار (Cascade) چیست؟
☐ ترتیب اعمال استایل‌ها
☐ اولویت‌بندی (Specificity) - مهم‌ترین بخش:
   - Inline Styles: 1000 امتیاز
   - ID Selector: 100 امتیاز
   - Class, Attribute, Pseudo-class: 10 امتیاز
   - Element, Pseudo-element: 1 امتیاز
   - Universal Selector: 0 امتیاز
☐ محاسبه امتیاز Specificity با مثال
☐ قانون !important و معایب آن
☐ ترتیب شکستن تساوی:
   1. Specificity
   2. Order of Appearance (ترتیب ظاهر شدن)
   3. !important
☐ چرا !important بد است؟
☐ بهترین شیوه‌ها:
   - اجتناب از !important
   - اجتناب از Inline CSS
   - ساختار انتخابگرهای قابل نگهداری
☐ DevTools و بررسی Specificity
☐ وراثت (Inheritance):
   - کدام خصوصیت‌ها ارث‌بری می‌کنند؟
   - کدام خصوصیت‌ها ارث‌بری نمی‌کنند؟
   - مثال‌های ارث‌بری (color, font-size)
☐ کنترل وراثت:
   - inherit
   - initial
   - unset
   - revert
☐ تمرین: حل تعارض‌های CSS
```

---

## 🔹 فصل ۷: موقعیت‌دهی (Position & Layout)
**ساعت: ۴**

```
☐ جریان عادی سند (Normal Flow)
☐ خصوصیت display:
   - block
   - inline
   - inline-block
   - none (مخفی کردن المان)
☐ خصوصیت position:
   - static (پیش‌فرض)
   - relative (نسبی)
   - absolute (مطلق)
   - fixed (ثابت)
   - sticky (چسبنده)
☐ مختصات موقعیت‌دهی:
   - top
   - right
   - bottom
   - left
☐ نقطه مرجع در position absolute:
   - اولین والد position: relative
   - مشکل z-index
☐ z-index و لایه‌بندی المان‌ها
☐ خصوصیت float:
   - left, right, none
   - پاکسازی float با clearfix
   - مشکلات float در CSS مدرن
☐ خصوصیت visibility:
   - visible (پیش‌فرض)
   - hidden (مخفی ولی فضا اشغال می‌کند)
   - collapse
☐ overflow:
   - visible (پیش‌فرض)
   - hidden (مخفی)
   - scroll (اسکرول)
   - auto (در صورت نیاز)
☐ کاربرد display: none vs visibility: hidden
☐ تمرین: ساخت منوی ناوبری ثابت (Sticky)
```

---

## 🔹 فصل ۸: شبه‌کلاس‌ها و شبه‌عناصر
**ساعت: ۳**

```
☐ تفاوت Pseudo-class و Pseudo-element
☐ Syntax (نحو نوشتار):
   - شبه‌کلاس: selector:pseudo-class
   - شبه‌عنصر: selector::pseudo-element
☐ شبه‌کلاس‌های لینک و تعامل:
   - :link
   - :visited
   - :hover
   - :active
   - :focus
☐ شبه‌کلاس‌های ساختاری:
   - :first-child
   - :last-child
   - :nth-child(n)
   - :nth-child(even)
   - :nth-child(odd)
   - :nth-child(2n+1)
   - :only-child
   - :first-of-type
   - :last-of-type
☐ شبه‌کلاس‌های فرم:
   - :checked
   - :disabled
   - :enabled
   - :focus
   - :invalid
   - :valid
   - :required
   - :optional
   - :in-range
   - :out-of-range
☐ شبه‌کلاس‌های متنی:
   - :first-letter (::first-letter)
   - :first-line (::first-line)
☐ شبه‌عناصر:
   - ::before
   - ::after
   - ::placeholder
   - ::selection
☐ ساخت آیکون با ::before و ::after
☐ خصوصیت content و مقادیر آن
☐ کاربردهای عملی:
   - ساخت Tooltip با CSS خالص
   - استایل‌دهی فرم‌ها
   - جلوه‌های hover
☐ تمرین: ساخت منوی Dropdown با CSS خالص
```

---

## 📝 پروژه‌های درس

| پروژه | توضیح |
|-------|-------|
| **پروژه ۱** | استایل‌دهی صفحه مقاله با تمام مباحث تایپوگرافی |
| **پروژه ۲** | ساخت کارت محصول با Box Model و گرادیان |
| **پروژه ۳** | ساخت منوی ناوبری با Position و Hover |
| **پروژه ۴** | ساخت فرم ورود زیبا با شبه‌کلاس‌های فرم |
| **پروژه ۵** | بازسازی صفحه HTML درس قبل با CSS |

---

## 📚 منابع پیشنهادی

| نوع | منبع |
|-----|------|
| 📖 مستندات | [MDN CSS Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics) |
| 🎥 ویدیویی | دوره‌های CSS سایت CSS-Tricks |
| 🏆 تمرین | [FreeCodeCamp CSS](https://www.freecodecamp.org/learn/2022/responsive-web-design/) |
| 🛠️ ابزار | [Specificity Calculator](https://specificity.keegan.st/) |
| 🎨 ابزار | [CSS Gradient Generator](https://cssgradient.io/) |

---

## ⚠️ نکات مهم تدریس

```
✅ تمرکز بر تمرین عملی در هر جلسه
✅ استفاده از DevTools برای درک بهتر Box Model
✅ توضیح Specificity با مثال‌های واقعی
✅ مقایسه روش‌های مختلف position با پروژه عملی
✅ تاکید بر نام‌گذاری استاندارد
```

---

> **🔔 پیش‌نیاز:** گذراندن درس HTML & Semantic
> 
> **🔔 همراه:** همزمان با CSS Basics می‌توان تمرین‌های HTML قبلی را استایل‌دهی کرد