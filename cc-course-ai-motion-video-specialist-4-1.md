## After Effects Essentials: A 10-Minute Beginner's Guide

![[Pasted image 20260922170700.png]]
در این ویدیو آموزش ۱۰ دقیقه ای افتر افکت رو مشاهده میکنید.
https://www.youtube.com/watch?v=hb2bbfiNBXA
---
# **درسنامه: آشنایی با Adobe After Effects و ساخت اولین Motion**

## **هدف درس**

در این درس با محیط Adobe After Effects آشنا می‌شوید و یاد می‌گیرید یک Animation ساده را از ابتدا بسازید، کنترل کنید و خروجی بگیرید.

در پایان درس باید بتوانید:

- ساختار اصلی محیط After Effects را توضیح دهید.
- یک Composition ایجاد و تنظیم کنید.
- بتوانید Assetهای پروژه را سازمان‌دهی کنید.
- بتوانید Layer ایجاد و مدیریت کنید.
- با Keyframe یک Animation ساده بسازید.
- بتوانید Position، Scale، Rotation و Opacity را متحرک کنید.
- از Easy Ease برای بهبود حرکت استفاده کنید.
- با میانبرهای اصلی Timeline سریع‌تر کار کنید.
- بتوانید Text Layer ایجاد و تنظیم کنید.
- از Pre-composition برای مدیریت Animationهای پیچیده‌تر استفاده کنید.
- یک Composition را برای خروجی گرفتن آماده کنید.

---
# **۱. After Effects چیست؟**

نرم افزار **Adobe After Effects** برای ساخت و ترکیب عناصر متحرک و جلوه‌های بصری است.
در Motion Design، After Effects بیشتر برای کارهایی مانند این استفاده می‌شود:

- Motion Graphics
- Text Animation
- Logo Animation
- Animated Infographics
- تبلیغات ویدیویی
- Title Sequence
- UI Animation
- Visual Effects
- Compositing

یکی از مفاهیم اصلی در After Effects این است:
شما عناصر مختلف را در یک فضای زمانی قرار می‌دهید و مشخص می‌کنید این عناصر در طول زمان چگونه تغییر کنند.

برای مثال:

```text
Text
   ↓
Position
   ↓
Keyframes
   ↓
Movement
```

![[Pasted image 20260922171805.png]]

---
# **۲. ساختار اصلی محیط After Effects**
وقتی After Effects را باز می‌کنید، با چند بخش اصلی مواجه می‌شوید.
سه بخش برای شروع اهمیت بیشتری دارند:
### **Project Panel**
محل مدیریت Assetهای پروژه است.
مثلاً:
- Video
- Image
- Audio
- Illustrator File
- Photoshop File
- Composition

![[Pasted image 20260922172038.png]]

![[Pasted image 20260922173708.png]]

---
### **Composition Panel**

محل مشاهده نتیجه کار است.
هر چیزی که در Composition قرار دهید، در این پنجره مشاهده می‌شود.

![[Pasted image 20260922173842.png]]



---
### **Timeline**
بخش Timeline جایی است که Animation را کنترل می‌کنید.

در Timeline مشخص می‌کنیم:

- چه Layerهایی وجود دارند.
- هر Layer چه زمانی دیده شود.
- چه زمانی حرکت کند.
- ویژگی (Property) های آن ها در طول زمان چگونه تغییر کنند.

![[Pasted image 20260922173631.png]]

---
# **۳. Composition چیست؟**

بخش **Composition** محیط اصلی‌ای است که Animation شما در آن ساخته می‌شود.
هر Composition دارای مشخصاتی مانند Width، Height، Frame Rate، Duration، Background است.

![[Pasted image 20260922173501.png]]

![[Pasted image 20260922173605.png]]

---
# **۴. سازمان‌دهی پروژه**

پروژه‌های Motion Design می‌توانند خیلی سریع شلوغ شوند.
اگر تمام فایل‌ها را بدون ساختار وارد Project Panel کنیم، پیدا کردن Assetها دشوار می‌شود.
بنابراین بهتر است Assetها را دسته‌بندی کنیم.

مثلاً:

```text
PROJECT
│
├── 01_COMPS
├── 02_VIDEO
├── 03_IMAGES
├── 04_AUDIO
├── 05_GRAPHICS
├── 06_FONTS
└── 07_EXPORTS
```

همچنین نام‌گذاری فایل‌ها باید واضح باشد.
هدف این است که چند روز یا چند هفته بعد نیز بتوانیم سریع بفهمیم هر فایل چیست.

---
# **۵. Layer چیست؟**

هر عنصر موجود در Composition معمولا در قالب یک **Layer** قرار می‌گیرد.
مثلا یک Composition ممکن است شامل این Layerها باشد:

```text
Text
Logo
Background
Video
Music
Shape
```

هر Layer Propertyهای مخصوص خود را دارد.
یکی از مهم‌ترین مجموعه Propertyها، **Transform** است.

![[Pasted image 20260922173309.png]]

---
## **Transform Properties**

![[Pasted image 20260922173159.png]]

بخش **Transform** برای کنترل موقعیت و ظاهر Layer استفاده می‌شود:

- **Position:** تغییر موقعیت Layer
- **Scale:** تغییر اندازه Layer
- **Rotation:** چرخاندن Layer
- **Opacity:** تغییر میزان شفافیت Layer

این چهار Property از اصلی‌ترین ابزارهای ساخت Animation در After Effects هستند.

---
# **۶. Keyframe چیست؟**

مفهوم **Keyframe** یکی از بنیادی‌ترین مفاهیم Animation در After Effects است. Keyframe به After Effects می‌گوید:
«در این لحظه، مقدار این Property باید این باشد.»

مثلا:

```text
0s                                                            2s
│                                                                │
Position = 0                                         Position = 500
●──────────────────────●
Keyframe                                              Keyframe
```

ما فقط مقدار ابتدا و انتها را مشخص کرده‌ایم.
خود After Effects تغییر بین این دو مقدار را محاسبه می‌کند.

بنابراین:

```text
Keyframe 1
     ↓
Interpolation‌(درون‌یابی)
     ↓
Keyframe 2
```

باعث ایجاد Animation می‌شود.

![[Pasted image 20260922173127.png]]

---
# **۷. ساخت اولین Animation**
فرض کنید یک Shape داریم و می‌خواهیم از سمت چپ صفحه وارد شود.

![[Pasted image 20260922174430.png]]

با استفاده از آیکون ساعت می‌توانید، KeyFrame ایجاد کنید، با جا به جا کردن Playhead یا Current Time Indicator (CTI) که نام دیگر آن است، می‌توانید دو Keyframe ایجاد کنید، اگر مقدار Property در دو Keyframe متفاوت باشد، شکل شما Animate میشود.

---
# **۸. Linear Motion**
به‌صورت پیش‌فرض، یک حرکت می‌تواند به شکل **Linear** باشد.
در این حالت سرعت حرکت تقریباً ثابت است:

```text
سرعت
│
│ ─────────────
│
└────────────── زمان
```

مثلا یک Object در هر لحظه با سرعت مشابه حرکت می‌کند. این نوع حرکت همیشه اشتباه نیست، اما در بسیاری از Motionها می‌تواند بیش از حد مکانیکی به نظر برسد.

---
# **۹. Easy Ease**

برای ایجاد حرکت نرم‌تر می‌توان از **Easy Ease** استفاده کرد.
در After Effects، میانبر رایج آن:

**F9**

است.

اما نکته مهم این است که Easy Ease یک «افکت جادویی» نیست؛ فقط یکی از روش‌های کنترل **Interpolation** است.
برای کنترل حرفه‌ای‌تر حرکت، باید با **Graph Editor** و انواع Easing آشنا شوید.

![[Pasted image 20260922180609.png]]

## Graph Editor
بعد از زدن F9 روی Keyframe ها دکمه ![[Pasted image 20260922181128.png]] رو بزنید.

![[Pasted image 20260922181145.png]]

اگر که همچین نموداری رو ندیدید، یا F9 نزدید، یا پوزیشن یا Keyframe هاتون رو انتخاب و فعال نکردین.

![[Pasted image 20260922181247.png]]

با انتخاب کردن مثلا Position نمودار را فعال کنید.

![[Pasted image 20260922180909.png]]

حالا میتوانید با کشیدن دایره های زرد به داخل موشن خودتون رو نرم تر کنید. به این صورت:

![[Pasted image 20260922181522.png]]

---
# **۱۰. میانبرهای مهم**

یادگیری میانبرهای Propertyها سرعت کار را افزایش می‌دهد.

|**کلید**|**Property**|
|---|---|
|**P**|Position|
|**S**|Scale|
|**R**|Rotation|
|**T**|Opacity|
|**U**|نمایش Propertyهای دارای Keyframe|
|**F9**|Easy Ease|

نکته: ابتدا باید لایه خود را فعال کرده باشین، برای F9 هم باید Keyframe هارو انتخاب کرده باشین.

https://helpx.adobe.com/after-effects/desktop/get-started/keyboard-shortcuts/keyboard-shortcuts-reference.html

---
# **۱۱. Pre-Composition چیست؟**

فرض کنید یک Animation شامل این Layer ها است:

```text
Logo
Text
Shape 1
Shape 2
Glow
Background
```

اگر بخواهیم این مجموعه را به‌عنوان یک واحد در Composition دیگری استفاده کنیم، می‌توانیم آن‌ها را **Pre-compose** کنیم.

در نتیجه:

```text
Logo
Text
Shape
Effects
   ↓
Pre-comp
   ↓
یک Layer
```

حالا Pre-comp مانند یک واحد مستقل قابل استفاده است.
## **آموزش Pre-compose در After Effects**

1. لایه هایی که می‌خواهید با هم ترکیب شوند را در **Timeline** انتخاب کنید.
2. راست‌کلیک کنید.
3. گزینه **Pre-compose…** را بزنید.
4. برای Pre-comp یک نام مشخص انتخاب کنید؛ مثلاً:  
    `Logo_Animation`
5. یکی از گزینه‌های انتقال Attributeها را انتخاب کنید.
6. روی **OK** بزنید.

حالا Layerهای انتخاب‌شده به یک **Pre-comp Layer** تبدیل می‌شوند.

```text
قبل:

Text
Logo
Shape
Background


بعد:

Logo_Animation
Background
```

### **ورود به داخل Pre-comp**

روی Pre-comp دوبار کلیک کنید تا Composition داخلی آن باز شود و Layerهای اصلی را ببینید.

### **چرا از Pre-compose استفاده می‌کنیم؟**

مهم‌ترین کاربردها:

- مرتب کردن Timeline
- ساده‌تر کردن پروژه‌های شلوغ
- ترکیب چند Layer به‌عنوان یک واحد
- استفاده مجدد از یک Animation
- اعمال Effect روی چند Layer به‌صورت همزمان

### **میانبر**

در ویندوز:

**Ctrl + Shift + C**

در مک:

**Cmd + Shift + C**

این میانبر مستقیماً پنجره **Pre-compose** را باز می‌کند.

---
# **۱۲. چرا Pre-comp مهم است؟**
انجام دادن Pre-comp برای سه کار بسیار مفید است:
### **مدیریت پیچیدگی پروژه**
چندین Layer را می‌توان در قالب یک واحد مدیریت کرد.
### **استفاده دوباره**
یک Animation را می‌توان در چند Composition استفاده کرد.
### **Consistency**
به‌جای ساختن سه Logo Animation جداگانه، می‌توان یک Animation ساخت و چند بار استفاده کرد.

آموزش ساخت Precompose:
https://www.youtube.com/watch?v=xLcSAfNAAzw

---
# **۱۳. Effects**

نرم افزار After Effects مجموعه بزرگی از Effects دارد.
یکی از نمونه‌های ساده:

**Hue/Saturation**
که می‌تواند برای تغییر ویژگی‌های رنگی Footage یا Layer استفاده شود.

اما باید توجه داشت:

افکت با Motion Design یکی نیست. افکت‌ها ابزار هستند.

یک Motion Designer ابتدا باید تصمیم بگیرد **چه چیزی و چرا باید تغییر کند** و سپس از Effect مناسب استفاده کند.

آموزش کامل 190 افکت در After Effect:
https://youtube.com/playlist?list=PLjNI3J96cKVKmujglFYJEkHzZwpwJ45LV&si=59zsbE51UX-My_t6

---
# **۱۴. Rendering**
آموزش رندرینگ در افتر افکت:
https://youtu.be/qE9672A5VkU?si=pLJ1KuoShZW78HJT

---
# **۲۰. Master و Delivery File**

بهتر است بین فایل تولیدی و فایل نهایی برای انتشار تفاوت قائل شویم.
یک Workflow معمول می‌تواند این باشد:

```text
After Effects
      ↓
Master Render
      ↓
Adobe Media Encoder
      ↓
Compressed Version
      ↓
Web / Social Media
```

برای مثال، ممکن است یک خروجی با کیفیت بالا به‌عنوان Master نگهداری شود و سپس نسخه‌ای با حجم کمتر برای انتشار در وب ساخته شود.
فرمت **H.264** یکی از فرمت‌های رایج برای Delivery و انتشار آنلاین است.

---

# **21. Workflow ساده یک پروژه Motion**

اکنون می‌توان کل فرآیند را در یک مسیر ساده دید:

```text
1. Create Project
        ↓
2. Organize Assets
        ↓
3. Create Composition
        ↓
4. Create Layers
        ↓
5. Design
        ↓
6. Add Keyframes
        ↓
7. Adjust Timing
        ↓
8. Add Easing
        ↓
9. Add Text / Graphics
        ↓
10. Pre-compose if needed
        ↓
11. Review
        ↓
12. Render
        ↓
13. Compress / Deliver
```

این Workflow قرار نیست برای همه پروژه‌ها دقیقاً یکسان باشد، اما ساختار ذهنی مناسبی برای شروع کار ایجاد می‌کند.

---

# **تمرین عملی**

یک Composition ساده بسازید و این Animation را ایجاد کنید:

### **صحنه**

یک پس‌زمینه ساده، یک عنوان و یک دایره داشته باشید.

### **Animation**

1. دایره از خارج صفحه وارد شود.
2. دایره با Position حرکت کند.
3. حرکت آن با Easy Ease تنظیم شود.
4. عنوان با Opacity از 0 به 100 برسد.
5. عنوان کمی بعد از ورود دایره ظاهر شود.
6. دایره کمی Scale شود.
7. پروژه را با ساختار منظم در Project Panel ذخیره کنید.
8. در پایان یک خروجی ویدیویی بگیرید.

### **هدف تمرین**

در این تمرین باید این مفاهیم را عملاً استفاده کنید:

**Composition → Layer → Transform → Keyframe → Timing → Easing → Text → Rendering**

اگر توانستید این تمرین را بدون دنبال کردن مرحله‌به‌مرحله آموزش انجام دهید، مفاهیم پایه این درس را تا حد مناسبی یاد گرفته‌اید.