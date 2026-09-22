این یک راهنمای سریع (Cheat Sheet) برای زبان **YAML** (YAML Ain't Markup Language) است. YAML زبانی برای پیکربندی (Configuration) و انتقال داده‌ها است که بر پایه‌ی خوانایی انسان تمرکز دارد.

### ۱. ساختار کلی
YAML از **فاصله‌گذاری (Indentation)** برای نشان دادن سلسله‌مراتب استفاده می‌کند.
- **توجه مهم:** هرگز از `Tab` استفاده نکنید. همیشه از **۲ یا ۴ فاصله (Space)** استفاده کنید.

---

### ۲. انواع داده‌ها

#### الف) رشته‌ها (Strings)
```yaml
name: Ali
description: این یک متن ساده است
quote: 'این هم یک متن با کاراکترهای خاص " و ' است'
multi_line: |
  این متن در چند خط
  ادامه پیدا می‌کند
  اما خط‌های جدید حفظ می‌شوند.
multi_line_folded: >
  این متن در چند خط
  نوشته شده اما
  در خروجی به صورت یک خط
  ترکیب می‌شود.
```

#### ب) اعداد (Numbers)
```yaml
age: 25
price: 19.99
hex: 0x1F
binary: 0b1010
not_a_number: "123"  # اگر عدد را داخل کوتیشن بگذارید، رشته محسوب می‌شود
```

#### ج) مقادیر منطقی (Booleans)
```yaml
is_active: true
is_deleted: no
enabled: yes
disabled: off
```

#### د) لیست‌ها (Lists / Arrays)
دو روش برای تعریف لیست وجود دارد:

**روش خطی:**
```yaml
fruits:
  - Apple
  - Banana
  - Cherry
```

**روش آرایه‌ای (برای داده‌های ساده‌تر):**
```yaml
colors: [Red, Green, Blue]
```

#### هـ) اشیاء/دیکشنری‌ها (Objects / Maps)
```yaml
user:
  name: Sara
  age: 30
  address:
    city: Tehran
    zip: 12345
```

---

### ۳. نکات مهم و رایج

#### کپی کردن ارجاعات (Aliases & Anchors)
برای جلوگیری از تکرار کد از `&` (انکر) و `*` (ارجاع) استفاده کنید.

```yaml
defaults: &defaults
  adapter: postgres
  host: localhost

development:
  <<: *defaults  # مقادیر defaults را اینجا کپی می‌کند
  database: dev_db

test:
  <<: *defaults
  database: test_db
```

#### کامنت‌گذاری
برای نوشتن توضیحات از علامت `#` استفاده کنید.

```yaml
# این یک کامنت است
name: Ali # این هم یک کامنت در انتهای خط است
```

#### تبدیل نوع داده (Type Casting)
اگر YAML یک مقدار را به اشتباه به نوع دیگری تبدیل کرد (مثلاً `"08"` را به عدد ۸)، می‌توانید نوع آن را مجبور کنید:

```yaml
# تبدیل به رشته
string_val: !!str 08

# تبدیل به عدد
int_val: !!int "123"
```

#### چندین سند در یک فایل (Multi-document)
اگر می‌خواهید چندین فایل YAML را در یک فایل واحد داشته باشید، از `---` استفاده کنید:

```yaml
---
name: Ali
age: 25
---
name: Sara
age: 30
```

---

### ۴. تفاوت‌های کلیدی با JSON
| ویژگی | YAML | JSON |
| :--- | :--- | :--- |
| **خوانایی** | بسیار بالا (انسان‌خوان) | کمتر خوانا |
| **توضیحات** | پشتیبانی از کامنت (`#`) | کامنت ندارد |
| **فرمت** | مبتنی بر فاصله (Indentation) | مبتنی بر آکولاد `{}` |
| **کاربرد** | پیکربندی (Config) | تبادل داده (API) |

---

### ۵. مثال کامل یک فایل پیکربندی (مثال Docker Compose یا GitLab CI)

```yaml
version: '3.8'

services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./html:/usr/share/nginx/html
    environment:
      - ENV=production
      - DEBUG=false
    depends_on:
      - db

  db:
    image: postgres:13
    environment:
      POSTGRES_PASSWORD: secret_password
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:
```

