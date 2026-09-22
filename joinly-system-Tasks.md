# 📋 **Joinly - Task List**

---
## 🎯 **Phase 1: Setup & Migration**

- [x] Replace Drizzle with Prisma ORM
- [x] Update database schema (prisma/schema.prisma)
- [x] Apply migrations to PostgreSQL
- [x] Configure Supabase Auth integration
- [x] Setup environment variables (.env.example)

---

## 🔐 **Phase 2: Authentication**

- [x] Login page (`/[locale]/auth/login/page.tsx`)
- [x] Signup page (`/[locale]/auth/signup/page.tsx`)
- [x] Auth actions (`modules/auth/actions/auth.actions.ts`)
- [x] Auth service (`modules/auth/services/auth.service.ts`)
- [x] Auth repository (`modules/auth/repository/auth.repository.ts`)
- [x] Login form component (`modules/auth/components/login-form.tsx`)
- [x] Signup form component (`modules/auth/components/signup-form.tsx`)
- [x] Validation schemas with Zod (`modules/auth/validation/`)

---
حذف ویژگی دوزبانه بودن:
- [x] auth/login/page.tsx
- [x] auth/login/page.tsx
- [x] src/app/dashboard/page.tsx
- [x] src/app/enrollment
- [x] login-form.tsx
- [x] signup-form.tsx
- [x] enrollment.actions.ts
- [x] enrollment-page.tsx




### پرامپت ۳: لایه Server Actions (لایه ارتباط با کلاینت)

> "حالا فایل `src/modules/todo/actions/todo.actions.ts` را بنویس. توابع این فایل باید توسط فرانت‌اند فراخوانی شوند. هر تابع باید: ۱. ابتدا با استفاده از یک تابع فرض شده مثل `getAuthUser` هویت کاربر را چک کند. ۲. تابع مربوطه از `todo.repository` را فراخوانی کند. ۳. از `revalidatePath` استفاده کند تا داده‌ها آپدیت شوند. مدیریت خطا (Try/Catch) هم فراموش نشود."


وصل کردن به Auth
### پرامپت ۴: لایه رابط کاربری (UI)

> "حالا کامپوننت `src/modules/todo/components/todo-list.tsx` را بنویس. این کامپوننت باید از کامپوننت‌های UI موجود در پروژه (که قبلاً با shadcn نصب کردم) استفاده کند. ۱. برای لیست کردن از `Card` استفاده کن. ۲. برای تیک زدنِ کارها از `Checkbox` (shadcn) استفاده کن. ۳. برای ورودیِ متنِ کارِ جدید از `Input` (shadcn) استفاده کن و برای دکمه‌ی افزودن از `Button` (shadcn). ۴. ظاهرِ صفحه را با Tailwind تمیز و مرتب کن. ۵. از `useTransition` برای نمایش حالت Loading در دکمه‌ها و چک‌باکس‌ها استفاده کن تا تجربه کاربری نرمی داشته باشیم."
## 🏫 **Phase 3: Academy Management**

- [ ] Academy repository (`modules/academy/repository/academy.repository.ts`)
- [ ] Academy service (`modules/academy/services/academy.service.ts`)
- [ ] Academy actions (`modules/academy/actions/academy.actions.ts`)
- [ ] Academy types (`modules/academy/types/`)

---

## 📚 **Phase 4: Course & Learning Path**

- [ ] Course repository (`modules/course/repository/course.repository.ts`)
- [ ] Course service (`modules/course/services/course.service.ts`)
- [ ] Course actions (`modules/course/actions/course.actions.ts`)
- [ ] Learning Path repository (`modules/learning-path/repository/learning-path.repository.ts`)
- [ ] Learning Path service (`modules/learning-path/services/learning-path.service.ts`)

---

## 📝 **Phase 5: Enrollment System**

- [ ] Enrollment repository (`modules/enrollment/repository/enrollment.repository.ts`)
- [ ] Enrollment service (`modules/enrollment/services/enrollment.service.ts`)
- [ ] Enrollment actions (`modules/enrollment/actions/enrollment.actions.ts`)
- [ ] Enrollment validation (`modules/enrollment/validation/`)
- [ ] Course catalog component (`modules/enrollment/components/course-catalog.tsx`)
- [ ] Selected courses component (`modules/enrollment/components/selected-courses.tsx`)
- [ ] Unit progress component (`modules/enrollment/components/unit-progress.tsx`)
- [ ] Enrollment page (`/[locale]/enrollment/page.tsx`)
- [ ] Enrollment rules utils (`modules/enrollment/utils/enrollment-rules.ts`)

---

## 📊 **Phase 6: Dashboard**

- [ ] Dashboard repository (`modules/dashboard/repository/dashboard.repository.ts`)
- [ ] Dashboard service (`modules/dashboard/services/dashboard.service.ts`)
- [ ] Dashboard actions (`modules/dashboard/actions/dashboard.actions.ts`)
- [ ] Dashboard page (`/[locale]/dashboard/page.tsx`)

---

## 🎨 **Phase 7: UI & Visual Identity**

- [ ] Apply brand colors (purple, white, dark)
- [ ] Update typography system (`config/typography.ts`)
- [ ] Update spacing system (`config/spacing.ts`)
- [ ] Update shadow system (`config/shadow.ts`)
- [ ] Update radius system (`config/radius.ts`)
- [ ] Create reusable Card component with subtle border
- [ ] Create Button component (CTA style)
- [ ] Create Input component
- [ ] App header component (`components/layout/app-header.tsx`)
- [ ] App shell component (`components/layout/app-shell.tsx`)
- [ ] Add Glow effects to Hero sections
- [ ] Implement responsive design (Desktop → Tablet → Mobile)

---

## 🌐 **Phase 8: Internationalization (i18n)**

- [ ] English dictionary (`i18n/dictionaries/en/common.json`)
- [ ] English enrollment dictionary (`i18n/dictionaries/en/enrollment.json`)
- [ ] Persian dictionary (`i18n/dictionaries/fa/common.json`)
- [ ] Persian enrollment dictionary (`i18n/dictionaries/fa/enrollment.json`)
- [ ] i18n config (`i18n/config.ts`)

---

## 🛠️ **Phase 9: Infrastructure**

- [ ] Database client setup (`lib/db.ts`)
- [ ] Supabase client (`lib/supabase/client.ts`)
- [ ] Supabase server (`lib/supabase/server.ts`)
- [ ] Error handling (`lib/errors.ts`)
- [ ] Logger (`lib/logger.ts`)
- [ ] API response types (`types/api.ts`)
- [ ] Middleware setup (`middleware.ts`)

---

## ✅ **Phase 10: Quality & Documentation**

- [ ] Write README.md
- [ ] Update project_structure.md
- [ ] ESLint configuration
- [ ] TypeScript strict mode
- [ ] Remove unused dependencies
- [ ] Final testing

---

## 📌 **Notes**

- **Prisma** is the ORM (not Drizzle)
- **Supabase Auth** for authentication
- **Zod** for validation
- **shadcn/ui** for UI components
- **Tailwind CSS** for styling
- **i18n** for Persian & English support

---

**Status**: 🟡 In Progress | 🟢 Completed | ⚪ Pending