در اینجا یک **راهنمای سریع (Cheat Sheet)** برای زبان اس‌وی‌جی (SVG) آورده شده است. این راهنما شامل تگ‌های اصلی، ویژگی‌های کلیدی و نکات کاربردی برای طراحی و کدنویسی وکتورها است.

---

### 1. ساختار پایه (Skeleton)
هر فایل SVG با تگ `<svg>` شروع می‌شود.

```xml
<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <!-- محتوای گرافیکی در اینجا قرار می‌گیرد -->
</svg>
```

- `width` / `height`: اندازه ظاهری.
- `viewBox`: مختصات داخلی (مهم برای ریسپانسیو بودن).
- `xmlns`: نام فضای نام استاندارد SVG.

---

### 2. اشکال هندسی پایه (Basic Shapes)

| شکل | تگ | ویژگی‌های کلیدی |
| :--- | :--- | :--- |
| **مستطیل** | `<rect>` | `x`, `y`, `width`, `height`, `rx` (گوشه گرد) |
| **دایره** | `<circle>` | `cx`, `cy`, `r` (شعاع) |
| **بیضی** | `<ellipse>` | `cx`, `cy`, `rx` (شعاع افقی), `ry` (شعاع عمودی) |
| **خط** | `<line>` | `x1`, `y1` (شروع), `x2`, `y2` (پایان) |
| **پلی‌لاین** | `<polyline>` | `points` (مجموعه مختصات) |
| **پلی‌گون** | `<polygon>` | `points` (مجموعه مختصات بسته) |

**مثال مستطیل با گوشه گرد:**
```xml
<rect x="10" y="10" width="80" height="80" rx="10" fill="blue" />
```

---

### 3. مسیرهای سفارشی (Paths - `<path>`)
قدرتمندترین تگ SVG که با دستور `d` کار می‌کند.

**دستورات اصلی:**
- `M` (MoveTo): حرکت به مختصات جدید (`M x y`)
- `L` (LineTo): کشیدن خط (`L x y`)
- `C` (Cubic Bezier): منحنی درجه سوم (`C cx1 cy1, cx2 cy2, x y`)
- `S` (Smooth Bezier): منحنی نرم (`S cx2 cy2, x y`)
- `Q` (Quadratic Bezier): منحنی درجه دوم (`Q cx cy, x y`)
- `A` (Arc): کمان (`A rx ry rotation large-arc-flag sweep-flag x y`)
- `Z` (ClosePath): بستن مسیر

**مثال:**
```xml
<path d="M 10 10 L 90 90 M 90 10 L 10 90" stroke="black" stroke-width="2" />
```

---

### 4. استایل‌دهی (Styling)

می‌توانید از CSS درون‌خطی یا تگ `<style>` استفاده کنید.

**ویژگی‌های مهم:**
- `fill`: رنگ داخل شکل (پیش‌فرض: سیاه).
- `stroke`: رنگ مرز شکل (پیش‌فرض: none).
- `stroke-width`: ضخامت مرز.
- `opacity`: شفافیت کل.
- `fill-opacity`: شفافیت پرکننده.
- `stroke-dasharray`: خط‌چین کردن مرز (مثال: `stroke-dasharray="5,5"`).

**مثال CSS:**
```css
.my-shape {
  fill: #3498db;
  stroke: #2980b9;
  stroke-width: 2px;
  transition: all 0.3s ease;
}
.my-shape:hover {
  fill: #e74c3c;
}
```

---

### 5. گروه‌بندی و انتقال (Grouping & Transform)

**گروه‌بندی (`<g>`):**
برای اعمال استایل یا ترنسفورم مشترک روی چندین عنصر.

```xml
<g transform="translate(50, 50) rotate(45)">
  <circle cx="0" cy="0" r="20" fill="red" />
  <rect x="-10" y="-10" width="20" height="20" fill="blue" />
</g>
```

**توابع ترنسفورم:**
- `translate(x, y)`: جابجایی.
- `rotate(angle, cx, cy)`: چرخش.
- `scale(sx, sy)`: تغییر اندازه.
- `skewX(angle) / skewY(angle)`: کج کردن.

---

### 6. گرادینت‌ها (Gradients)

برای ایجاد رنگ‌های ترکیبی از دو یا چند رنگ استفاده می‌شود.

**الف) گرادینت خطی (`<linearGradient>`):**
```xml
<defs>
  <linearGradient id="myGrad" x1="0%" y1="0%" x2="100%" y2="0%">
    <stop offset="0%" stop-color="red" />
    <stop offset="100%" stop-color="blue" />
  </linearGradient>
</defs>
<rect width="100" height="100" fill="url(#myGrad)" />
```

**ب) گرادینت شعاعی (`<radialGradient>`):**
```xml
<defs>
  <radialGradient id="radGrad" cx="50%" cy="50%" r="50%">
    <stop offset="0%" stop-color="yellow" />
    <stop offset="100%" stop-color="orange" />
  </radialGradient>
</defs>
<circle cx="50" cy="50" r="40" fill="url(#radGrad)" />
```

---

### 7. فیلترها و افکت‌ها (Filters)

برای ایجاد سایه، بلور و افکت‌های دیگر.

**مثال سایه (`<feDropShadow>`):**
```xml
<defs>
  <filter id="shadow" x="-20%" y="-20%" width="140%" height="140%">
    <feDropShadow dx="2" dy="4" stdDeviation="3" flood-color="#000" flood-opacity="0.5" />
  </filter>
</defs>
<rect x="10" y="10" width="80" height="80" fill="green" filter="url(#shadow)" />
```

---

### 8. متون (Text)

```xml
<text x="50" y="50" font-family="Arial" font-size="20" fill="white" text-anchor="middle">
  Hello SVG
</text>
```

- `text-anchor`: تراز افقی (`start`, `middle`, `end`).
- `dominant-baseline`: تراز عمودی.

---

### 9. نکات طلایی (Best Practices)

1.  **ریسپانسیو:** همیشه از `viewBox` استفاده کنید تا SVG در هر اندازه‌ای به درستی اسکیل شود.
2.  **بهینه‌سازی:** قبل از استفاده در وب، فایل SVG را با ابزارهایی مثل [SVGOMG](https://jakearchibald.github.io/svgomg/) بهینه کنید تا حجم آن کاهش یابد.
3.  **دقت:** از مختصات اعشاری با دقت مناسب استفاده کنید (معمولاً ۲ رقم اعشار کافی است).
4.  **تگ `<defs>`:** هر چیزی که قرار است فقط تعریف شود و مستقیماً رندر نشود (مثل گرادینت، پترن، فیلتر)، باید داخل `<defs>` قرار گیرد.
5.  **انیمیشن:** می‌توانید از CSS Animation یا تگ‌های داخلی `<animate>` و `<animateTransform>` برای متحرک‌سازی استفاده کنید.

**مثال انیمیشن ساده با CSS:**
```css
@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
.spinner {
  animation: spin 2s linear infinite;
}
```

---
این Cheat Sheet پوشش‌دهنده اکثر نیازهای روزمره در طراحی و توسعه وب با SVG است.