

ساختار کلی هر فصل
1) مقدمه مفهومی
2) توضیح عمیق مفاهیم
3) مثال‌های کدنویسی
4) توضیح خط‌به‌خط کد
5) نکات حرفه‌ای (Best Practices)
6) تمرین‌ها: ساده، متوسط، چالشی

بخش ۱
---

---
### **ورود به دنیای نرم‌افزار**
1. مقدمه
2. مرور نقشه پروژه نهایی: پلتفرم مدیریت KPI  
3. چی هست Next.js و چرا با آن شروع می‌کنیم؟  
4. صرفاً ابزارهای لازم (Node.js، VS Code، browser)  
5. ساخت اولین سایت «سلام دنیا!» با Next.js

---

### **مفاهیم**
1. شناخت ساختار پروژه در Next.js (pages، components، API)  
2. فهم JSX (چطور HTML و JavaScript یکی می‌شوند؟)  
3. استایل دادن آسان: CSS و Tailwind در عمل  
4. داده‌ها از کجا می‌آیند؟ آشنایی اولیه با state و props  
5. تمرین کوچک: ساخت کارت KPI جعلی

---

### **طراحی رابط کاربری پلتفرم KPI**
1. طراحی صفحه داشبورد ساده  
2. ساخت فهرست کارمندان و نمره عملکردشان  
3. افزودن آیکون‌ها، رنگ‌های سازمانی و نمودارها  
4. ساخت کامپوننت‌های قابل‌استفاده‌مجدد (Mini Design System)  
5. تمرین پروژه: طراحی رابط کامل نسخه MVP

---

### **ساخت API و اتصال به داده‌های واقعی**
1. ساخت API داخلی با Next.js  
2. استفاده از داده‌های Mock و JSON  
3. معرفی مفاهیم CRUD (Create، Read، Update، Delete) با مثال‌های واقعی  
4. ذخیره داده‌ها در Local Storage یا فایل ساده  
5. تست و اشکال‌زدایی API‌ها

---

### **افزودن منطق و تعاملات**
1. افزودن فرم‌های ورود KPI (ورودی هدف، نمره، توضیحات)  
2. جمع‌آوری داده‌ها از چند بخش  
3. مدیریت state با React Hooks  
4. فیلتر و جستجو در داده‌ها  
5. تمرین: افزودن KPI جدید و مشاهده لیست

---

### **تمرکز روی تجربه کاربری واقعی**
1. اضافه کردن احراز هویت ساده (login & logout بدون سرور)  
2. طراحی مسیرهای خصوصی برای مدیران  
3. نمایش امتیاز کل و عملکرد کلی کارمندان  
4. ساخت صفحه گزارش‌ها و نمودارهای تحلیلی  
5. تمرین: ساخت گزارش ماهانه KPI

---

### **آماده‌سازی برای دنیای واقعی**
1. معرفی پایگاه داده واقعی (مثلاً SQLite یا Supabase)  
2. آپلود نسخه آزمایشی روی اینترنت (Vercel Deploy)  
3. بهینه‌سازی سرعت و سئو در Next.js  
4. نوشتن کد تمیز و قابل نگهداری  
5. جمع‌بندی: از پروژه تمرینی تا محصول واقعی

---

### **ضمیمه‌ها**
- نکات ذهنی برای فکر کردن مثل برنامه‌نویس  
- منابع و مسیرهای بعدی یادگیری (React، TypeScript، DevOps و غیره)  
- تمرین‌های پیشنهادی برای بعد از کتاب  

---
بخش ۲
---

### فصل 0: مبانی شی‌گرایی (۸–۱۲ ساعت)
####  شی‌گرایی چیست؟
- تفاوت پارادایم Functional و OOP
- چرا و کِی OOP مفید است
####  شیء در JavaScript
- Object Literal
- Property و Method
- دسترسی و زمینه this در اشیا

####  Constructor Function
- قبل از class در ES6
- مفهوم نمونه (Instance) و new

####  Class در ES6
- تعریف class
- constructor
- method
- تفاوت class با function و نحوه transpile شدن

####  this در جاوااسکریپت
- this در methodهای کلاس/شی
- this در arrow function
- اشتباهات رایج (binding، call/apply/bind)

####  Encapsulation (کپسوله‌سازی)
- public در مقابل private
- فیلدهای خصوصی: #privateField
- چرا مهم است؟ کنترل دسترسی، API سطح شی، کاهش کوپلینگ

####  Inheritance (ارث‌بری)
- extends
- super
- چه زمانی استفاده نکنیم (ترجیح ترکیب بر ارث‌بری در موارد پیچیده)

####  OOP در یک پروژه واقعی Node.js
- لایه‌ها: Controller / Service / Repository
- یک مثال ساده معماری و جریان داده

### فصل 1: پیش‌نیازهای JavaScript مدرن (۸–۱۲ ساعت)
- مرور ES6+ (let/const، arrow function، destructuring، spread/rest، template literal)
- Async / Await
- Promise و Callback
- کار با JSON
- مروری بر HTTP و REST

### فصل 2: معرفی Node.js (۲–۳ ساعت)
- Node.js چیست و چگونه کار می‌کند
- تفاوت Node.js با JavaScript در مرورگر
- نصب Node.js و npm
- اجرای اولین برنامه Node
- کار با REPL در Node

### فصل 3: ماژول‌ها در Node.js (۴–۶ ساعت)
- مفهوم Module و ایزوله‌سازی
- CommonJS: require / module.exports
- ES Modules: import / export
- ماژول‌های داخلی Node: fs, path, os, http
- نکات سازگاری CJS/ESM

### فصل 4: کار با فایل‌ها (File System) (۴–۵ ساعت)
- خواندن و نوشتن فایل (sync/async/promise-based)
- حذف و ویرایش فایل
- کار با Streamها (Readable/Writable/Transform)
- مدیریت خطا و backpressure به‌صورت مقدماتی

### فصل 5: مدیریت پکیج‌ها با npm (۲–۳ ساعت)
- npm چیست
- نصب پکیج‌ها (dependencies/devDependencies)
- package.json و scripts
- قفل نسخه‌ها و مدیریت dependency ها
- استفاده از npx

### فصل 6: ساخت سرور با Node.js (۵–۷ ساعت)
- ماژول http
- ایجاد سرور ساده
- مدیریت request و response
- Routing ساده بدون فریمورک
- ساختن لایه Config ساده

### فصل 7: فریمورک Express.js (۱۲–۱۵ ساعت)
- نصب و راه‌اندازی Express
- ساخت REST API
- Routing در Express (Router، params، query)
- Middleware (built-in, third-party, custom)
- مدیریت خطا (error-handling middleware)
- ساختاردهی پروژه Express

### فصل 8: کار با دیتابیس (۱۰–۱۴ ساعت)
- اتصال به MongoDB
- استفاده از Mongoose
- عملیات CRUD
- طراحی Schema و Model
- اعتبارسنجی (Validation) و میدلورهای Mongoose

### فصل 9: احراز هویت و امنیت (۸–۱۰ ساعت)
- JWT Authentication
- Hash کردن رمز عبور با bcrypt
- Middleware احراز هویت و مجوزها (Authorization)
- نکات امنیت API (rate limiting, helmet, CORS, input sanitization)

### فصل 10: مدیریت فایل و آپلود (۴–۵ ساعت)
- آپلود فایل با Multer
- ذخیره‌سازی و نام‌گذاری امن فایل‌ها
- مدیریت تصاویر (فشرده‌سازی، تغییر اندازه)

### فصل 11: تست در Node.js (۵–۶ ساعت)
- تست واحد با Jest یا Mocha
- تست API (supertest)
- الگوهای Arrange-Act-Assert
- Mock/Stubs/Fakes
- پوشش کد و اجرای تست در CI

### فصل 12: مفاهیم پیشرفته Node.js (۸–۱۰ ساعت)
- Event Loop و فازها
- Streams عمیق‌تر (pipeline، backpressure، highWaterMark)
- Cluster
- Worker Threads
- Performance Optimization (profiling، monitoring، caching)

### فصل 13: ساخت پروژه واقعی
- طراحی RESTful API انتهابه‌انتها
- ساخت سیستم Login/Register
- Pagination و Filtering
- نسخه‌بندی API و مدیریت خطا
- مستندسازی (Swagger/OpenAPI)

### فصل 14: آماده‌سازی و استقرار (Deployment) (۲۰–۲۵ ساعت)
- آماده‌سازی برای Production (env، logging، config)
- استفاده از PM2 (clustering، مراقبت سرویس)
- Deploy روی VPS
- Docker: ساخت image، نوشتن Dockerfile، docker-compose
- نکات مقیاس‌پذیری و رصد (metrics، healthchecks)

### الگوی تمرین‌های پایان فصل
- تمرین ساده: تثبیت مفاهیم کلیدی با محدوده کوچک
- تمرین متوسط: کاربرد چند مفهوم با سناریوی نیمه‌واقعی
- تمرین چالشی: مینی‌پروژه یا مسئله باز با تأکید بر طراحی

