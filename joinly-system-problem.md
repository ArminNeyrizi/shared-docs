این خلاصه‌ی فنی و دقیق برای اینکه بتوانید به یک چت جدید یا یک هوش مصنوعی دیگر بدهید تا دقیقاً در جریان پروژه قرار بگیرد:

موضوع پروژه: توسعه اپلیکیشن با معماری Modular Monolith (Next.js + Prisma + Supabase + Tailwind + shadcn/ui).

خلاصه‌ی وضعیت فعلی:

۱. مدیریت دیتابیس: سیستم از دستور ناپایدار db push به سیستم استاندارد prisma migrate مهاجرت کرده است. دیتابیس فعلاً برای همگام‌سازی کامل، Reset شده و تمام جداول (User, Student, Todo, Course و غیره) با موفقیت ساخته شده‌اند.

۲. معماری ماژولار: پروژه از الگوی ماژولار در مسیر src/modules/... استفاده می‌کند. ماژول todo به صورت زیر پیاده‌سازی شده:

Repository: مدیریت کوئری‌های دیتابیس.

Actions: توابع Server Actions (شامل create, toggle, delete, findAll) با استفاده از revalidatePath و مدیریت خطا.

Components: کامپوننت TodoList (کلاینت ساید) با استفاده از shadcn/ui و useTransition برای نمایش حالت Loading.

۳. وضعیت کد:

مدل‌های پریسما در schema.prisma نهایی شده‌اند.

تمام ارتباطات (Relations) شامل User -> Todo و User -> Student برقرار است.

۴. مشکل فعلی:
دکمه های sign up و login کار نمیکنن
فکر میکنم به این خاطر هست که اینا با student کار میکردن نه با user
شاید
