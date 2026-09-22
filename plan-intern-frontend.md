# **پلن ۹۰ روزه کارآموز Frontend**

**مدت:** ۲۳ شهریور تا ۲۲ آذر ۱۴۰۵  
**هدف نهایی:** توانایی گرفتن یک Feature واقعی از Task تا Production

### **Stack پیشنهادی**

```text
HTML
CSS
JavaScript
TypeScript
React
Next.js
Tailwind CSS
shadcn/ui
Git/GitHub
REST API
Supabase
Testing
Deployment
```

---

# **فاز ۱ — پایه + Git**

### **۲۳ شهریور تا ۵ مهر**

|**هفته**|**تمرکز**|**خروجی**|
|---|---|---|
|۱|HTML + CSS + Git|Landing Page|
|۲|Responsive + JavaScript|Interactive Landing Page|

### **هفته ۱**

یادگیری:

- Semantic HTML
- Forms
- Flexbox
- Grid
- Position
- Responsive Design
- Git
- GitHub

**پروژه:**

یک Landing Page برای یک دوره آموزشی.

باید:

```text
Navbar
Hero
Features
Course Cards
Pricing
FAQ
Footer
```

داشته باشد.

### **هفته ۲**

JavaScript:

- Variables
- Functions
- Arrays
- Objects
- DOM
- Events
- Fetch
- async/await

**پروژه:**

Course Catalog با:

- Search
- Filter
- Sort
- Modal
- Form validation

---

# **فاز ۲ — React**

### **۶ تا ۱۹ مهر**

## **هفته ۳**

React fundamentals:

- Components
- Props
- State
- Events
- Conditional Rendering
- Lists

پروژه:

**Course Card System**

---

## **هفته ۴**

React:

- useState
- useEffect
- Forms
- API calls
- Loading
- Error states
- Component composition

پروژه:

**Course Listing**

داده‌ها از API یا JSON بیایند.

---

# **فاز ۳ — TypeScript + UI**

### **۲۰ مهر تا ۳ آبان**

## **هفته ۵**

TypeScript:

```text
type
interface
union
generic
optional properties
type narrowing
```

تمام پروژه React هفته قبل را TypeScript کن.

---

## **هفته ۶**

UI Engineering:

- Tailwind
- shadcn/ui
- Design tokens
- Responsive
- Accessibility
- reusable components

ساخت:

```text
Button
Input
Select
Modal
Card
Table
Badge
Tabs
Dropdown
```

هدف:

**Component Library کوچک**

---

# **فاز ۴ — Next.js**

### **۴ تا ۱۷ آبان**

## **هفته ۷**

Next.js:

- App Router
- Layout
- Pages
- Dynamic Routes
- Metadata
- Loading
- Error
- Not Found

پروژه:

```text
/courses
/courses/[slug]
```

---

## **هفته ۸**

Next.js واقعی:

- Server Components
- Client Components
- Data Fetching
- Route Handlers
- Environment Variables
- SEO

پروژه:

**Mini Academy Website**

مثلاً:

```text
Home
Courses
Course Detail
Instructors
About
Contact
```

---

# **فاز ۵ — Backend Integration**

### **۱۸ آبان تا ۱ آذر**

## **هفته ۹**

Supabase:

- Database
- Query
- Insert
- Update
- Delete
- Authentication

پروژه:

**Course Dashboard**

---

## **هفته ۱۰**

Auth:

```text
Login
Register
Logout
Protected Routes
User Profile
Role
```

Roleها:

```text
student
instructor
admin
```

---

# **فاز ۶ — پروژه واقعی**

### **۲ تا ۱۵ آذر**

از اینجا دیگر **Tutorial ممنوع**.

کارآموز باید وارد Repository واقعی شود.

## **هفته ۱۱**

یک Feature واقعی دریافت کند.

مثلاً:

ساخت صفحه Course Detail

Task باید شامل:

```text
Figma / Reference
Requirements
Acceptance Criteria
Deadline
```

باشد.

کارآموز:

```text
Branch
↓
Implementation
↓
Commit
↓
Pull Request
↓
Code Review
↓
Fix
```

را انجام دهد.

---

## **هفته ۱۲**

Feature دوم:

مثلاً:

**Student Dashboard**

شامل:

- Courses
- Progress
- Continue Learning
- Profile

---

# **فاز ۷ — Production**

### **۱۶ تا ۲۲ آذر**

## **هفته ۱۳**

کارآموز یک Feature را از ابتدا تا انتها انجام می‌دهد.

مثلاً:

**Course Management**

```text
Create Course
↓
Edit Course
↓
Publish Course
↓
Course Page
```

و باید:

- Responsive باشد.
- Error handling داشته باشد.
- Loading state داشته باشد.
- Git history تمیز داشته باشد.
- PR داشته باشد.
- Deploy شده باشد.

---

# **برنامه هفتگی کارآموز**

با دانشگاه، برنامه را این‌طور نگه می‌دارم:

|**روز**|**زمان**|**کار**|
|---|---|---|
|شنبه|۲h|Learning|
|یکشنبه|۲h|Coding|
|دوشنبه|۲h|Coding|
|سه‌شنبه|۳h|Deep Work|
|چهارشنبه|۲h|Project|
|پنجشنبه|۲h|Project|
|جمعه|۲h|Review / Fix|

**جمع: ۱۵ ساعت**

سه‌شنبه چون روز آزاد دانشگاه است، باید تبدیل شود به **روز اصلی توسعه**.

---

# **سیستم Task**

هر Task باید کوچک باشد.

بد:

صفحه Dashboard را بساز.

خوب:

```text
FE-021
Create Dashboard Layout

Acceptance Criteria:
□ Responsive
□ Sidebar
□ Header
□ Mobile navigation
□ Empty state
□ Loading state

Estimate: 2h
```

---

# **سیستم Code Review**

هر PR فقط با این ۶ سؤال بررسی شود:

```text
1. درست کار می‌کند؟
2. Responsive است؟
3. Componentها قابل استفاده مجددند؟
4. TypeScript درست استفاده شده؟
5. Code ساده است؟
6. آیا چیزی را می‌توان حذف کرد؟
```

آخرین سؤال برای این مسیر مهم است:

**What did you undesign?**

اگر کارآموز برای یک Feature ساده ۷ component و ۳ abstraction ساخته، احتمالاً طراحی بیش از حد پیچیده است.

---

# **KPI کارآموز**

در پایان ۹۰ روز:

|**KPI**|**Target**|
|---|---|
|Git Commits|80+|
|Pull Requests|12+|
|Completed Tasks|30+|
|Mini Projects|3|
|Production Features|2–3|
|Code Reviews|15+|
|Deployed Projects|3|
|Documentation|100%|

اما **تعداد commit معیار اصلی نیست**. معیار اصلی این است که بتواند یک Feature واقعی را بدون hand-holding کامل کند.

---

# **سطح مورد انتظار در پایان ۹۰ روز**

### **هفته ۱–۴**

**Junior Beginner**

می‌تواند UI بسازد.

### **هفته ۵–۸**

**Junior Frontend**

می‌تواند React/Next.js پروژه بزند.

### **هفته ۹–۱۰**

**Product Frontend**

می‌تواند API و Auth را وصل کند.

### **هفته ۱۱–۱۳**

**Team Member**

می‌تواند Task واقعی بگیرد، PR بزند، Review بگیرد و Feature را Deploy کند.

---

## **مسیر یادگیری را هم این‌طور قفل می‌کنم**

```text
HTML/CSS
    ↓
JavaScript
    ↓
React
    ↓
TypeScript
    ↓
Tailwind/shadcn
    ↓
Next.js
    ↓
API
    ↓
Supabase
    ↓
Git/PR
    ↓
Real Feature
    ↓
Production
```

**چیز اضافه‌ای تا وقتی این زنجیره کامل نشده وارد برنامه نمی‌شود.**