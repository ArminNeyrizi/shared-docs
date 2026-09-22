

#### **1. Auth + User Identity**

اول این را حل می‌کنیم:

```text
یک User در Joinly
        │
        ├── Student
        ├── Instructor
        ├── Admin
        └── ...
```

و مشخص می‌کنیم:

- Login / Register
- Session
- Role / Permission
- User ↔ Payload
- User ↔ NestJS
- دسترسی مدرس به Course و Lesson
- دسترسی Admin
- جلوگیری از ایجاد Userهای duplicate

**هدف:** یک هویت کاربری، نه چند سیستم احراز هویت موازی.

---

#### **2. Course CMS برای مدرس**

بعد کاری می‌کنیم که مدرس برای انتشار دوره **اصلاً نیاز به کدنویسی نداشته باشد**.

مثلاً:

```text
Create Course
│
├── اطلاعات دوره
├── تصویر
├── مدرس
├── دسته‌بندی
├── سرفصل‌ها
│    ├── فصل ۱
│    │    ├── درس ۱
│    │    ├── درس ۲
│    │    └── ...
│    └── فصل ۲
│
├── محتوای Lesson
├── فایل‌ها
├── ویدیو
└── انتشار
```

یعنی به جای:

```text
content/
   probability/
      ...
         .mdx
```

مدرس از Payload استفاده کند.

---

#### **3. Learning Content Engine**

اینجا قابلیت‌های محتوای آموزشی را اضافه می‌کنیم:

```text
Lesson
│
├── Text
├── Heading
├── Image
├── Video
├── File
├── Code
├── Table
├── Formula / LaTeX
├── Quiz
├── Callout
└── Interactive
```

برای LaTeX هم می‌توانیم چیزی مثل:

```latex
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
```

را داخل ادیتور قرار دهیم و در Frontend با KaTeX رندر کنیم.

تو همین الان `katex` و `react-katex` را داری، بنابراین این بخش از صفر نیست.

---

#### **4. Interactive Content**

بعد می‌رویم سراغ چیزی شبیه H5P، ولی **از ساده‌ترین مدل ممکن** شروع می‌کنیم.

مثلاً:

```text
Interactive
├── Multiple Choice
├── True / False
├── Fill in the Blank
├── Matching
├── Drag & Drop
├── Interactive Diagram
└── Custom HTML/JS Component
```

و ساختار محتوا می‌تواند چیزی شبیه این باشد:

```text
Lesson
  ↓
Blocks
  ↓
┌───────────────┐
│ Text          │
│ Formula       │
│ Image         │
│ Video         │
│ Quiz          │
│ Interactive   │
└───────────────┘
```

این معماری خیلی بهتر از این است که برای هر نوع Lesson یک صفحه جدا در Next.js بسازیم.

---

# **چیزی که فعلاً نمی‌سازیم**

برای جلوگیری از شلوغ شدن Joinly، فعلاً این‌ها را وارد پروژه نمی‌کنیم:

```text
❌ H5P کامل
❌ سیستم LMS عظیم
❌ Editor اختصاصی از صفر
❌ چند Authentication Provider
❌ Microservice
❌ چند Database
❌ CMS جداگانه
❌ سیستم Plugin پیچیده
```

اول یک **Content Block System تمیز** می‌سازیم. اگر بعداً نیاز واقعی به قابلیت پیچیده‌ای بود، اضافه می‌کنیم.

---

## **ترتیب اجرای واقعی**

من این ترتیب را پیشنهاد می‌کنم:

```text
01
Auth + Identity
        ↓
02
Roles & Permissions
        ↓
03
Course / Lesson Data Model
        ↓
04
Teacher Course Publishing
        ↓
05
Rich Text + Images + Files
        ↓
06
Video
        ↓
07
LaTeX
        ↓
08
Interactive Blocks
        ↓
09
Course Frontend Redesign
        ↓
10
Student Learning Experience
```

**یک تغییر کوچک نسبت به ترتیب تو:**  
زیباسازی فرانت دوره‌ها را بعد از مدل محتوا انجام می‌دهم، نه قبلش. چون اگر اول UI را بسازیم و بعد ساختار Course/Lesson تغییر کند، احتمالاً دوباره بخش زیادی از Frontend را بازنویسی می‌کنیم.

برای شروع، **Auth + یکپارچه‌سازی Userها** را انجام می‌دهیم. برای این مرحله اول `backend/package.json` و `frontend/collections/Users.ts` را بررسی می‌کنم تا دقیقاً بر اساس معماری فعلی Joinly پیاده‌سازی کنیم.