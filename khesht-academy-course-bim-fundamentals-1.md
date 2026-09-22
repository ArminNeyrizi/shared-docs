## **۱. مبانی و مفهوم BIM**

### **1.1 BIM چیست؟**

**BIM = Building Information Modeling**

اما ترجمه‌ی «مدل‌سازی اطلاعات ساختمان» کمی گمراه‌کننده است؛ چون BIM صرفاً مدل‌سازی سه‌بعدی ساختمان نیست.

BIM یک **روش برای تولید، مدیریت، تبادل و استفاده از اطلاعات پروژه در طول چرخه عمر ساختمان** است.

به زبان ساده:

در BIM، ما فقط ساختمان را نمی‌کشیم؛ اطلاعات ساختمان را به شکلی ساختاریافته ایجاد و مدیریت می‌کنیم.

مثلاً در CAD ممکن است یک دیوار فقط چند خط باشد:

```text
────────────
```

اما در BIM، یک دیوار می‌تواند یک عنصر واقعی با اطلاعاتی مثل این باشد:

```text
Wall
├── Type: Exterior Wall
├── Width: 20 cm
├── Height: 3 m
├── Material: Concrete
├── Fire Rating: 2h
├── Thermal Properties: ...
├── Cost: ...
└── Classification: ...
```

بنابراین وقتی ارتفاع طبقه تغییر می‌کند، مدل می‌تواند ارتباطات مربوط به آن دیوار را نیز مدیریت کند.

---

# **1.2 BIM از چه چیزی تشکیل شده است؟**

برای درک BIM بهتر است آن را حاصل ترکیب چهار جزء بدانیم:

### **People + Process + Technology + Information**

```text
                 BIM
                 │
      ┌──────────┼───────────┐
      │                             │                                 │
   People                   Process             Technology
      │                             │                                 │
      └──────── Information ---──┘
```

### **People**

افرادی که در پروژه فعالیت می‌کنند:

- Architect
- Structural Engineer
- MEP Engineer
- BIM Modeler
- BIM Coordinator
- BIM Manager
- Contractor
- Client
- Facility Manager

BIM بدون تعریف مسئولیت افراد، فقط استفاده از نرم‌افزار است.

---

### **Process**

فرآیند مشخص می‌کند:

- چه اطلاعاتی تولید شود؟
- چه کسی آن را تولید کند؟
- چه زمانی تولید شود؟
- کجا ذخیره شود؟
- چه کسی بررسی کند؟
- چه زمانی منتشر شود؟
- چگونه بین تیم‌ها منتقل شود؟

مثلاً:

```text
Architecture
     ↓
Structural Coordination
     ↓
MEP Coordination
     ↓
Clash Detection
     ↓
Issue Resolution
     ↓
Approved Model
```

---

### **Technology**

ابزارهایی که برای تولید و مدیریت اطلاعات استفاده می‌شوند.

مثلاً:

- Revit
- Civil 3D
- Tekla
- Archicad
- Navisworks
- Solibri
- Autodesk Construction Cloud
- BIMcollab
- Common Data Environment

نکته مهم:

**BIM مساوی Revit نیست.**

Revit یک ابزار برای اجرای بخشی از فرآیند BIM است.

---

### **Information**

مهم‌ترین بخش BIM همین Information است.

اطلاعات می‌تواند شامل موارد زیر باشد:

- Geometry
- Dimensions
- Materials
- Specifications
- Quantities
- Cost
- Schedule
- Manufacturer
- Performance
- Maintenance Data

مثلاً یک Door فقط یک شکل مستطیلی نیست:

```text
Door
│
├── Width = 900 mm
├── Height = 2100 mm
├── Material = Wood
├── Fire Rating = 60 min
├── Manufacturer = ...
├── Cost = ...
└── Asset ID = ...
```

---

# **1.3 تفاوت CAD و BIM**

یکی از اولین چیزهایی که دانشجو باید بفهمد این است که:

**CAD بیشتر روی ترسیم تمرکز دارد؛ BIM روی اطلاعات و ارتباط بین اطلاعات.**

مثلاً در یک نقشه CAD ممکن است برای نمایش یک پنجره چند خط رسم کنیم.

اما در BIM، پنجره یک **Object** است.

مثلاً:

```text
Window W-01

Width: 1200 mm
Height: 1500 mm
Frame: Aluminum
Glass: Double Glazed
U-Value: ...
Manufacturer: ...
```

بنابراین مدل فقط ظاهر پنجره را نمی‌داند؛ بلکه درباره‌ی پنجره **اطلاعات** دارد.

---

# **1.4 BIM فقط مدل سه‌بعدی نیست**

یک اشتباه رایج:

BIM یعنی ساختمان را سه‌بعدی مدل کنیم.

خیر.

مدل سه‌بعدی یکی از خروجی‌های BIM است.

مثلاً:

```text
              BIM
               │
     ┌───────┼───────---──┐
     ↓                     ↓                                 ↓
   3D Model        Data                Processes
     │                      │                                │
     ↓                      ↓                                 ↓
 Geometry     Quantities         Coordination
 Materials          Cost                     Information
```

ممکن است یک پروژه مدل سه‌بعدی داشته باشد ولی BIM واقعی نداشته باشد، اگر اطلاعات، فرآیندها، مسئولیت‌ها و تبادل اطلاعات به‌درستی تعریف نشده باشند.

---

# **1.5 BIM چه مشکلی را حل می‌کند؟**

فرض کنیم یک پروژه شامل سه تیم باشد:

```text
معماری
   +
سازه
   +
تأسیسات
```

در روش سنتی ممکن است هر تیم جداگانه کار کند.

مثلاً:

```text
Architect
   ↓
Drawing

Structural Engineer
   ↓
Structural Drawing

MEP Engineer
   ↓
MEP Drawing
```

بعد در زمان اجرا مشخص شود:

```text
کانال تأسیسات
      ↓
     ███
      ↓
     تیر
     ███
```

یعنی کانال از تیر عبور می‌کند.

در BIM می‌توان مدل‌های رشته‌های مختلف را با هم هماهنگ کرد:

```text
Architecture ──┐
               │
Structure ─────┼──→ Federated Model
               │
MEP ───────────┘
                      ↓
                Clash Detection
                      ↓
                Issue Resolution
```

در نتیجه بخشی از مشکلات می‌تواند **قبل از اجرا** شناسایی شود.

---

# **1.6 BIM در تمام عمر ساختمان استفاده می‌شود**

BIM فقط مربوط به مرحله طراحی نیست.

چرخه کلی:

```text
Planning
   ↓
Design
   ↓
Construction
   ↓
Handover
   ↓
Operation
   ↓
Maintenance
```

مثلاً اطلاعات یک تجهیز مکانیکی می‌تواند در مرحله طراحی ایجاد شود و بعداً در زمان بهره‌برداری استفاده شود:

```text
AHU-01

Model:
AHU-01

Manufacturer:
X

Capacity:
20,000 m³/h

Installation Date:
2027

Maintenance Interval:
6 months

Warranty:
2 years
```

بنابراین اطلاعات تولیدشده در طراحی می‌تواند در مراحل بعدی نیز ارزش داشته باشد.

---

# **1.7 BIM یک «مدل» نیست؛ یک سیستم اطلاعاتی پروژه است**

این تفکیک برای دانشجو خیلی مهم است.

سه مفهوم را از هم جدا کنیم:

### **Model**

نمایش دیجیتال عناصر ساختمان.

### **Information**

داده‌هایی که به عناصر و پروژه مربوط هستند.

### **Process**

روش تولید، بررسی، مدیریت و تبادل این اطلاعات.

پس:

```text
BIM
=
Model
+
Information
+
Process
+
People
+
Technology
```

به همین دلیل اگر کسی فقط Revit یاد بگیرد، الزاماً BIM یاد نگرفته است.

او ممکن است **BIM Authoring** یا مدل‌سازی اطلاعاتی را یاد گرفته باشد، اما هنوز موضوعاتی مثل Coordination، Information Management، CDE، BEP و ISO 19650 را نداند.

---

# **1.8 یک مثال کامل**

فرض کنیم می‌خواهیم یک ساختمان ۵ طبقه طراحی کنیم.

در روش BIM:

### **مرحله ۱ — معماری**

Architect مدل معماری را ایجاد می‌کند.

```text
Architecture Model
       ↓
Walls
Doors
Windows
Rooms
Floors
```

### **مرحله ۲ — سازه**

Structural Engineer مدل سازه را ایجاد می‌کند.

```text
Structural Model
       ↓
Columns
Beams
Slabs
Foundations
```

### **مرحله ۳ — تأسیسات**

MEP Engineer:

```text
MEP Model
       ↓
Ducts
Pipes
Equipment
Electrical Systems
```

### **مرحله ۴ — ترکیب**

مدل‌ها با هم هماهنگ می‌شوند:

```text
Architecture
      +
Structure
      +
MEP
      ↓
Federated Model
```

### **مرحله ۵ — بررسی**

مثلاً:

```text
Duct
 ↓
████████
     X
████████
 Beam
```

یک Clash پیدا می‌شود.

### **مرحله ۶ — اصلاح**

تیم‌ها موضوع را بررسی و طراحی را اصلاح می‌کنند.

### **مرحله ۷ — اجرا**

از اطلاعات تأییدشده برای:

- نقشه‌های اجرایی
- Quantity Takeoff
- برنامه‌ریزی
- هماهنگی اجرا

استفاده می‌شود.

### **مرحله ۸ — تحویل**

اطلاعات نهایی ساختمان برای مالک و بهره‌بردار باقی می‌ماند.

---

## **1.9 جمله‌ای که دانشجو باید از این بخش به خاطر بسپارد**

اگر بخواهیم کل این بخش را به یک مفهوم تبدیل کنیم:

**BIM یعنی مدیریت دیجیتال اطلاعات ساختمان و فرآیندهای مربوط به آن، از طراحی تا ساخت و بهره‌برداری.**

و سه اشتباه را نباید مرتکب شود:

**BIM ≠ Revit**

**BIM ≠ 3D Modeling**

**BIM ≠ فقط نرم‌افزار**

بلکه:

**BIM = People + Process + Technology + Information**


