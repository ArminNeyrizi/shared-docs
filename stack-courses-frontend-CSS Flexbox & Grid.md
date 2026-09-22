
# 📖 سرفصل درس CSS Flexbox & Grid

## واحد: ۱ | ساعت تدریس: ۱۵ ساعت

---

## 📋 ساختار کلی

| فصل | عنوان | ساعت |
|:---:|------|:---:|
| ۱ | آشنایی با Layout در CSS | ۱ |
| ۲ | Flexbox - مبانی و مفاهیم | ۱ |
| ۳ | Flexbox - خصوصیات Container | ۳ |
| ۴ | Flexbox - خصوصیات Item | ۳ |
| ۵ | Grid - مبانی و مفاهیم | ۱ |
| ۶ | Grid - خصوصیات Container | ۳ |
| ۷ | Grid - خصوصیات Item | ۲ |
| ۸ | ترکیب Flexbox و Grid + پروژه‌ها | ۱ |
| **جمع** | | **۱۵** |

---

## 🔹 فصل ۱: آشنایی با Layout در CSS
**ساعت: ۱**

```
☐ مشکلات روش‌های سنتی Layout:
   - float و مشکلات آن
   - inline-block و فاصله‌های ناخواسته
   - position و از دست دادن جریان سند
☐ تاریخچه Layout در CSS:
   - جداول (Table Layout)
   - Float-based Layout
   - Flexbox (از 2012)
   - Grid (از 2017)
☐ Flexbox vs Grid: چه زمانی از کدام استفاده کنیم؟
☐ مروری بر پشتیبانی مرورگرها
☐ آماده‌سازی محیط توسعه
☐ نگاه کلی به قابلیت‌های Flexbox و Grid
```

---

## 🔹 فصل ۲: Flexbox - مبانی و مفاهیم
**ساعت: ۱**

```
☐ Flexbox چیست؟ ( Flexible Box Layout )
☐ کاربردهای اصلی Flexbox
☐ مفاهیم پایه:
   - Flex Container (ظرف فلکس)
   - Flex Item (آیتم‌های فلکس)
   - Main Axis (محور اصلی)
   - Cross Axis (محور متقاطع)
   - Main Start / Main End
   - Cross Start / Cross End
☐ جهت محورها:
   - default: main axis = افقی (چپ به راست)
   - default: cross axis = عمودی (بالا به پایین)
☐ فعال‌سازی Flexbox با display: flex
☐ display: flex vs display: inline-flex
☐ نمایش بصری مدل Flexbox
☐ تفاوت flex-direction با direction
☐ تمرین: ساخت اولین Flex Container
```

---

## 🔹 فصل ۳: Flexbox - خصوصیات Container
**ساعت: ۳**

```
☐ flex-direction (جهت چیدمان):
   - row (پیش‌فرض)
   - row-reverse
   - column
   - column-reverse
   - توضیح effect روی Main Axis و Cross Axis
☐ justify-content (تراز در محور اصلی):
   - flex-start (پیش‌فرض)
   - flex-end
   - center
   - space-between
   - space-around
   - space-evenly
☐ align-items (تراز در محور متقاطع):
   - stretch (پیش‌فرض)
   - flex-start
   - flex-end
   - center
   - baseline
   - مثال تفاوت baseline با بقیه
☐ flex-wrap (شکستن خط):
   - nowrap (پیش‌فرض)
   - wrap
   - wrap-reverse
☐ align-content (تراز خطوط چندگانه):
   - فقط زمانی کار می‌کند که flex-wrap: wrap باشد
   - مقادیر: flex-start, flex-end, center, space-between, space-around, stretch
☐ gap (فاصله بین آیتم‌ها):
   - row-gap
   - column-gap
   - gap (مخفف)
   - مثال: gap: 20px یا gap: 10px 20px
☐ خلاصه: ۵ خصوصیت اصلی Container
   flex-direction, justify-content, align-items, flex-wrap, gap
☐ تمرین: ساخت Header با لوگو و منو
```

---

## 🔹 فصل ۴: Flexbox - خصوصیات Item
**ساعت: ۳**

```
☐ خصوصیت flex-grow (رشد):
   - مقدار پیش‌فرض: ۰
   - نحوه توزیع فضای اضافی
   - flex-grow: 1 برای تمام آیتم‌ها
   - نسبت‌های مختلف (1, 2, 3)
☐ خصوصیت flex-shrink (کوچک‌شدن):
   - مقدار پیش‌فرض: ۱
   - رفتار آیتم‌ها هنگام کمبود فضا
☐ خصوصیت flex-basis (اندازه پایه):
   - مقادیر: auto, 100px, 30%, ...
   - تفاوت با width
☐ مخفف flex:
   - flex: 1 (معادل flex-grow: 1; flex-shrink: 1; flex-basis: 0%)
   - flex: auto (معادل flex-grow: 1; flex-shrink: 1; flex-basis: auto)
   - flex: none (معادل flex-grow: 0; flex-shrink: 0; flex-basis: auto)
☐ خصوصیت align-self (تراز جداگانه):
   - auto, flex-start, flex-end, center, stretch, baseline
   - override کردن align-items Container
☐ خصوصیت order (ترتیب):
   - مقدار پیش‌فرض: ۰
   - ترتیب نمایش vs ترتیب DOM
   - کاربرد: responsive reorder
☐ الگوریتم محاسبه اندازه Flex Items
☐ تمرین‌های عملی:
   - ساخت Sidebar + Main + Aside Layout
   - ساخت کارت‌های Flex با رشد مساوی
   - ساخت Footer چسبنده
```

---

## 🔹 فصل ۵: Grid - مبانی و مفاهیم
**ساعت: ۱**

```
☐ CSS Grid چیست؟
☐ تفاوت Grid با Flexbox:
   - Flexbox: یک‌بعدی (یک ردیف یا یک ستون)
   - Grid: دوبُعدی (ردیف‌ها و ستون‌ها همزمان)
☐ مفاهیم پایه Grid:
   - Grid Container
   - Grid Item
   - Grid Line (خطوط)
   - Grid Track (ردیف‌ها و ستون‌ها)
   - Grid Cell (سلول)
   - Grid Area (ناحیه)
   - Grid Gap (فاصله)
☐ Terminology گرید:
   - Row Line 1, 2, 3...
   - Column Line 1, 2, 3...
☐ فعال‌سازی Grid با display: grid
☐ display: grid vs display: inline-grid
☐ نمایش بصری مدل Grid
☐ Grid vs Flexbox در عمل: چه زمانی از کدام استفاده کنیم؟
☐ تمرین: ساخت اولین Grid Container
```

---

## 🔹 فصل ۶: Grid - خصوصیات Container
**ساعت: ۳**

```
☐ تعریف ستون‌ها و ردیف‌ها:
   - grid-template-columns
   - grid-template-rows
☐ واحد fr (fraction):
   - grid-template-columns: 1fr 2fr 1fr
   - ترکیب fr با px و auto
   - مثال: 200px 1fr 1fr
☐ تکرار با repeat():
   - repeat(3, 1fr)
   - repeat(2, 100px 1fr)
   - repeat(auto-fit, minmax(200px, 1fr))
   - repeat(auto-fill, minmax(150px, 1fr))
☐ تابع minmax():
   - minmax(200px, 1fr)
   - minmax(min-content, max-content)
☐ الگوی Responsive بدون Media Query:
   grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))
☐ grid-template-areas:
   - تعریف ناحیه‌ها با نام
   - مثال:
     grid-template-areas:
       "header header header"
       "sidebar main aside"
       "footer footer footer";
   - استفاده از نقطه برای ناحیه خالی
☐ justify-items (تراز افقی آیتم‌ها):
   - stretch (پیش‌فرض)
   - start, end, center
☐ align-items (تراز عمودی آیتم‌ها):
   - stretch (پیش‌فرض)
   - start, end, center
☐ place-items (مخفف align-items + justify-items):
   - place-items: center
☐ justify-content (تراز کل گرید در Container افقی):
   - start, end, center, stretch
   - space-between, space-around, space-evenly
☐ align-content (تراز کل گرید در Container عمودی):
   - فقط زمانی کار می‌کند که Grid کوچک‌تر از Container باشد
☐ place-content (مخفف align-content + justify-content)
☐ gap در Grid:
   - row-gap, column-gap, gap
☐ implicit vs explicit Grid:
   - grid-template-rows (explicit)
   - grid-auto-rows (implicit)
   - grid-auto-columns
   - grid-auto-flow (row, column, dense)
☐ تمرین: ساخت Layout اصلی وبسایت (Header, Sidebar, Main, Footer)
```

---

## 🔹 فصل ۷: Grid - خصوصیات Item
**ساعت: ۲**

```
☐ grid-column و grid-row:
   - شروع و پایان با شماره خط
   - مثال: grid-column: 1 / 3
☐ سینتکس‌های مختلف:
   - grid-column: 1 / 3
   - grid-column: 1 / span 2
   - grid-column: 1 / -1 (آخرین خط)
   - grid-column-start: 1
   - grid-column-end: 3
☐ مخفف grid-area:
   - grid-area: row-start / col-start / row-end / col-end
☐ grid-area برای template-areas:
   - grid-area: header
   - grid-area: sidebar
☐ justify-self و align-self:
   - stretch (پیش‌فرض)
   - start, end, center
☐ place-self (مخفف)
☐ کاربرد z-index در Grid
☐ همپوشانی (Overlapping) آیتم‌ها:
   - قرار دادن دو آیتم روی یک سلول
☐ الگوریتم Auto Placement
☐ تمرین: ساخت گالری تصاویر با Grid
☐ تمرین: ساخت Dashboard با ستون‌ها و ردیف‌های متفاوت
```

---

## 🔹 فصل ۸: ترکیب Flexbox و Grid + پروژه‌ها
**ساعت: ۱**

```
☐ چرا ترکیب مهم است؟
☐ Grid برای Layout اصلی صفحه
☐ Flexbox برای چیدمان داخلی المان‌ها
☐ مثال Layout ترکیبی:
   ┌────────────────────────────────┐
   │  HEADER (Flexbox)              │
   ├──────────┬─────────────────────┤
   │          │                     │
   │ SIDEBAR  │  MAIN CONTENT       │
   │  (Grid)  │  (Grid + Flex)      │
   │          │                     │
   ├──────────┴─────────────────────┤
   │  FOOTER (Flexbox)             │
   └────────────────────────────────┘
☐ الگوی Holy Grail Layout با Grid
☐ ساخت Card Component با Flexbox داخل Grid
☐ مثال‌های واقعی از سایت‌های معروف
☐ نکات Performance
☐ مروری بر بهترین شیوه‌ها
☐ جمع‌بندی تفاوت‌ها و کاربردها
```

---

## 📝 پروژه‌های درس

| پروژه | توضیح |
|-------|-------|
| **پروژه ۱** | ساخت Header با Navigation (Flexbox) |
| **پروژه ۲** | ساخت Grid Gallery با تصاویر مختلف‌اندازه |
| **پروژه ۳** | ساخت Holy Grail Layout (Header + Sidebar + Main + Footer) |
| **پروژه ۴** | ساخت کارت‌های محصول Responsive بدون Media Query |
| **پروژه ۵** | ساخت Dashboard Admin با Grid و Flex ترکیبی |
| **پروژه ۶** | بازسازی Layout درس قبل (HTML+CSS) با Flex/Grid |

---

## 📊 جدول مقایسه Flexbox vs Grid

| ویژگی | Flexbox | Grid |
|-------|:-------:|:----:|
| بُعد | یک‌بعدی | دوبُعدی |
| چیدمان | ردیف **یا** ستون | ردیف **و** ستون |
| اندازه‌دهی آیتم‌ها | محتوا-محور | فضا-محور |
| ترتیب‌دهی | با order | با grid-area |
| کاربرد اصلی | منو، کارت‌ها، Navbar | Layout کل صفحه، گالری |
| responsive | دستی | خودکار (auto-fit) |

---

## 🛠️ ابزارهای کمکی

| ابزار | لینک |
|-------|------|
| Flexbox Visual | [flexboxfroggy.com](https://flexboxfroggy.com/) |
| Grid Garden | [cssgridgarden.com](https://cssgridgarden.com/) |
| CSS Grid Generator | [cssgrid-generator.netlify.app](https://cssgrid-generator.netlify.app/) |
| Flexbox Cheatsheet | [yoksel.github.io/flex-cheatsheet](https://yoksel.github.io/flex-cheatsheet/) |
| Grid Cheatsheet | [griddy.io](https://www.griddy.io/) |

---

## 📚 منابع پیشنهادی

| نوع | منبع |
|-----|------|
| 📖 مستندات | [MDN Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/Layout/Flexbox) |
| 📖 مستندات | [MDN Grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/Layout/Grids) |
| 🎥 ویدیویی | Traversal Media - Flexbox & Grid |
| 🏆 تمرین | [Flexbox Zombies](https://flexboxzombies.com/) |
| 📝 چک‌لیست | CSS-Tricks Complete Guide to Flexbox |
| 📝 چک‌لیست | CSS-Tricks Complete Guide to Grid |

---

## ⚠️ نکات مهم تدریس

```
✅ شروع با Flexbox (ساده‌تر) و سپس Grid
✅ تمرکز بر تفاوت‌ها و زمان استفاده از هرکدام
✅ استفاده از ابزارهای بصری مثل Flexbox Froggy
✅ توضیح auto-fit vs auto-fill با مثال عملی
✅ تمرکز روی Responsive بدون Media Query
✅ تاکید بر ترکیب صحیح Flex + Grid در پروژه واقعی
```

---

> **🔔 پیش‌نیاز:** گذراندن درس CSS Basics
>
> **🔔 همراه:** این درس پس‌زمینه HTML قوی نیاز دارد - مطمئن شوید دانشجویان تگ‌های ساختاری HTML را بلدند