<div align="center">

# 🔐 Security Blueprint — Universal Web App Spec
### نقشه‌ی جامع امنیت و مهندسی — پرامپت عمومی برای هر اپلیکیشن وب

[![Canvas](https://img.shields.io/badge/Obsidian-Canvas-7C3AED?logo=obsidian&logoColor=white)](https://obsidian.md)
[![Spec](https://img.shields.io/badge/Spec-Bilingual%20FA%20%2F%20EN-0E7490)](#)
[![Prompt](https://img.shields.io/badge/Use%20As-Prompt%20%2F%20Spec-9333EA)](#-use-it-as-a-prompt)
[![Frontend](https://img.shields.io/badge/Frontend-Next.js%20%2B%20React-111827?logo=nextdotjs&logoColor=white)](#)
[![Database](https://img.shields.io/badge/Database-MongoDB-47A248?logo=mongodb&logoColor=white)](#)
[![Security](https://img.shields.io/badge/Security-OWASP%20Top%2010-B91C1C)](#-owasp-top-10-checklist)

**🇬🇧 [English](#-english) · 🇮🇷 [فارسی](#-فارسی)**

</div>

---

<a id="english"></a>

## 🇬🇧 English

A **universal, project-agnostic security & engineering blueprint** for any web application built with **Next.js + MongoDB**. The entire spec lives in one interactive Obsidian Canvas file — organized into **6 color-coded categories** with step-by-step flow — so any developer (or AI coding agent) can pick it up and implement it without ambiguity. **Works for any project: dashboards, CRMs, shops, SaaS — anything.**

### 🚀 Use It as a Prompt

1. **Fork or copy** this repository (or just the canvas file) into your project
2. Open `Security-Blueprint.canvas` in [Obsidian](https://obsidian.md) — or any [JSON Canvas](https://jsoncanvas.org) compatible app
3. Hand it to your **developer or AI coding agent** as the security & engineering spec
4. Adapt the product-specific examples (upload whitelist, phone format, masked fields) to your own domain — everything else applies as-is

### 📂 Repository Contents

| File | Description |
|---|---|
| [`Security-Blueprint.canvas`](./Security-Blueprint.canvas) | The full interactive blueprint (Obsidian / JSON Canvas format) |
| `README.md` | This bilingual guide |

### 🗺 Blueprint Map — 6 Categories

The canvas follows a numbered flow (1 → 6) connected by arrows:

| # | Category | What it covers |
|---|---|---|
| 1 | 🏗 **Architecture & Tech Stack** | MongoDB (no migrations), React, Next.js + Node.js backend, SEO-first |
| 2 | 📁 **Folder Structure & Code Style** | Exact `src/` layout, clean code, component-driven scalability |
| 3 | 🚪 **Login Security** | Password hashing, rate limiting, unified errors, secure cookies, input validation |
| 4 | 🔑 **JWT Token System** | Access (2 min) + Refresh (15 days) tokens, 128-char secrets, cookie flags, logout |
| 5 | 🛡 **Post-Login Security** | Sessions, RBAC data isolation, IDOR, data masking, uploads, AI/chat, audit trail |
| 6 | 🐞 **OWASP Top 10 Checklist** | The 10 critical web threats with concrete fixes |

Every card inside the canvas is **English first, then Persian** (marked with 🇬🇧 / 🇮🇷).

### ✨ Security Highlights

| Area | Requirement |
|---|---|
| 🔑 Passwords | **Bcrypt / Argon2** only — plain text & MD5 forbidden |
| 🚦 Rate limit | Max **5 login requests / 15 min** per IP → temporary block |
| 💬 Errors | One unified message — never reveal whether username or password was wrong |
| 🍪 Token storage | JWT **only** in `HttpOnly` + `Secure` + `SameSite` cookies (XSS-proof) |
| ⏱ Sessions | Idle timeout 15–30 min · absolute timeout ~8 h · single active session per user |
| 🧱 Data isolation | Every query filtered by `user_id`; only admins see global reports |
| 😶 Data masking | Sensitive fields shown masked (e.g. `0912****567`); full view logged |
| 📎 Uploads | Whitelist (`jpg/png/pdf` + MIME), random names, no execute, cloud storage |
| 🤖 AI & Chat | Sanitized messages, rate + length limits on AI calls |
| 📜 Audit trail | IP + timestamp + username + action for every sensitive operation |

<a id="owasp-top-10-checklist"></a>

### 🐞 OWASP Top 10 Checklist

1. **SQL Injection** — sanitize every input (`' OR 1=1 --` must fail)
2. **XSS** (Reflected / Stored / DOM-based) — sanitize output & messages
3. **CSRF** — CSRF tokens + `SameSite=Strict/Lax` + re-auth for sensitive actions
4. **IDOR** — server-side ownership check per request, UUIDs
5. **Authentication Failures** — session regeneration, expiry, account lockout
6. **Sensitive Data Exposure** — HTTPS/TLS 1.2+/HSTS, encryption at rest & transit, secrets management, no stack traces, no API keys in frontend
7. **SSRF** — domain whitelist, block internal/loopback IPs, no auto redirects
8. **Security Misconfiguration** — hardening, no debug in prod, strict CORS, security headers
9. **Vulnerable Components** — regular updates, remove unused dependencies
10. **Unsafe File Uploads** — whitelist, random names, AV scan, no execute permission

> Reference: [github.com/OWASP/Top10](https://github.com/OWASP/Top10/)

### 🧰 Tech Stack

- **Database** → MongoDB — schema changes without migrations, painless updates
- **Frontend** → React — light and fast
- **Backend** → Next.js (App Router, `src/app/api/`) + Node.js patterns
- **SEO** → fully optimized on every public page

### 📁 Folder Structure

```text
src/
├── app/            → Frontend pages & routing
│   └── api/        → Backend & API routes
├── public/
│   ├── img/        → Site images
│   └── font/       → Site fonts
├── controllers/    → HTTP responses
├── services/       → All business logic
├── components/     → UI & styles (auth, theme, layout, ui)
└── utils/          → Libraries, realtime, helpers
.env                → Secrets: token keys, DB URI (never commit!)
```

### 📖 How to Open the Canvas

1. Install [Obsidian](https://obsidian.md) (free), open this folder as a vault
2. Click `Security-Blueprint.canvas`
3. Follow the numbered groups and arrows (1 → 6)

No Obsidian? Any app that supports the open [JSON Canvas](https://jsoncanvas.org) spec can read the file.

---

<a id="فارسی"></a>

<div dir="rtl">

## 🇮🇷 فارسی

یک **بلوپرینت عمومی و مستقل از نوع پروژه** برای امنیت و مهندسی هر اپلیکیشن وب با **Next.js + MongoDB**. کل اسپک در یک فایل کانواز تعاملی اوبسیدین است — با **۶ دسته‌بندی رنگی** و جریان مرحله‌به‌مرحله — تا هر توسعه‌دهنده (یا ایجنت هوش مصنوعی) بتواند بدون ابهام آن را پیاده‌سازی کند. **برای هر پروژه‌ای کار می‌کند: داشبورد، CRM، فروشگاه، SaaS — هر چیز.**

### 🚀 استفاده به‌عنوان پرامپت

1. این ریپو (یا فقط فایل کانواز) را **فورک یا کپی** کنید داخل پروژه‌ی خودتان
2. `Security-Blueprint.canvas` را در [Obsidian](https://obsidian.md) — یا هر برنامه‌ی سازگار با [JSON Canvas](https://jsoncanvas.org) — باز کنید
3. آن را به‌عنوان اسپک امنیتی و مهندسی به **توسعه‌دهنده یا ایجنت هوش مصنوعی** خود بدهید
4. مثال‌های وابسته به محصول (لیست آپلود مجاز، فرمت شماره تماس، فیلدهای ماسک‌شونده) را مطابق دامنه‌ی خودتان تنظیم کنید — بقیه بدون تغییر قابل اعمال است

### 📂 محتوای مخزن

| فایل | توضیح |
|---|---|
| [`Security-Blueprint.canvas`](./Security-Blueprint.canvas) | نقشه‌ی کامل تعاملی (فرمت اوبسیدین / JSON Canvas) |
| `README.md` | راهنمای دوزبانه (همین فایل) |

### 🗺 نقشه‌ی کانواز — ۶ دسته‌بندی

کانواز با جریان شماره‌دار (۱ تا ۶) و فلش‌های اتصال دنبال می‌شود:

| # | دسته | پوشش |
|---|---|---|
| ۱ | 🏗 **معماری و پشته‌ی فناوری** | MongoDB (بدون migration)، React، بک‌اند Next.js + Node.js، سئو محور |
| ۲ | 📁 **ساختار پوشه‌ها و سبک کد** | چیدمان دقیق `src/`، کد تمیز، کامپوننت‌محور و قابل‌توسعه |
| ۳ | 🚪 **امنیت ورود** | هش پسورد، محدودیت تلاش، خطای یکپارچه، کوکی امن، اعتبارسنجی ورودی |
| ۴ | 🔑 **سیستم توکن JWT** | توکن دسترسی (۲ دقیقه) + تازه‌سازی (۱۵ روز)، کلید ۱۲۸ کاراکتری، فلگ کوکی، خروج |
| ۵ | 🛡 **امنیت پس از ورود** | سشن، جداسازی داده RBAC، IDOR، ماسک اطلاعات، آپلود، چت و AI، لاگ‌گیری |
| ۶ | 🐞 **چک‌لیست OWASP Top 10** | ده تهدید بحرانی وب همراه راه‌حل مشخص |

هر کارت داخل کانواز **اول انگلیسی، بعد فارسی** است (با نشان 🇬🇧 / 🇮🇷).

### ✨ خلاصه‌ی الزامات امنیتی

| حوزه | الزام |
|---|---|
| 🔑 پسورد | فقط **Bcrypt / Argon2** — متن خام و MD5 ممنوع |
| 🚦 محدودیت تلاش | حداکثر **۵ درخواست لاگین در ۱۵ دقیقه** برای هر IP → بلاک موقت |
| 💬 خطاها | یک پیام یکپارچه — هرگز نگوید یوزرنیم اشتباه است یا پسورد |
| 🍪 نگهداری توکن | JWT فقط در کوکی‌های `HttpOnly` + `Secure` + `SameSite` (ضد XSS) |
| ⏱ سشن | انقضای بی‌فعالیتی ۱۵–۳۰ دقیقه · انقضای مطلق ~۸ ساعت · یک سشن فعال برای هر کاربر |
| 🧱 جداسازی داده | همه‌ی کوئری‌ها با فیلتر `user_id`؛ فقط مدیران گزارش‌های کلان را می‌بینند |
| 😶 ماسک داده | فیلدهای حساس به‌صورت ماسک (مثلاً `0912****567`)؛ نمایش کامل با ثبت لاگ |
| 📎 آپلود | Whitelist (پسوند + MIME)، نام رندوم، بدون دسترسی اجرا، فضای ابری |
| 🤖 چت و AI | پیام‌های Sanitize شده، محدودیت تعداد و طول درخواست‌های AI |
| 📜 لاگ حساس | آی‌پی + زمان + یوزرنیم + نوع عملیات برای هر اقدام حساس |

### 🐞 چک‌لیست OWASP Top 10

1. **تزریق SQL** — پاکسازی همه‌ی ورودی‌ها (شکست `' OR 1=1 --`)
2. **XSS** (Reflected / Stored / DOM) — پاکسازی خروجی و پیام‌ها
3. **CSRF** — توکن CSRF + کوکی `SameSite=Strict/Lax` + تایید مجدد عملیات حساس
4. **IDOR** — بررسی مالکیت در سمت سرور برای هر درخواست، UUID
5. **شکست احراز هویت** — بازتولید سشن، انقضا، قفل حساب
6. **افشای داده‌ی حساس** — HTTPS/TLS 1.2+/HSTS، رمزنگاری در Rest و Transit، مدیریت اسرار، بدون Stack Trace و API Key در فرانت
7. **SSRF** — whitelist دامنه، مسدودسازی IPهای داخلی، بدون redirect خودکار
8. **پیکربندی ناامن** — Hardening، بدون debug در پروداکشن، CORS سخت‌گیرانه، Security Headers
9. **کامپوننت‌های آسیب‌پذیر** — به‌روزرسانی منظم، حذف وابستگی‌های بلااستفاده
10. **آپلود ناامن** — whitelist، نام رندوم، اسکن آنتی‌ویروس، حذف دسترسی اجرا

> مرجع: [github.com/OWASP/Top10](https://github.com/OWASP/Top10/)

### 🧰 پشته‌ی فناوری

- **دیتابیس** → MongoDB — تغییرات شِما بدون migration، آپدیت بی‌دردسر
- **فرانت‌اند** → React — سبک و سریع
- **بک‌اند** → Next.js (App Router در `src/app/api/`) + الگوهای Node.js
- **سئو** → کاملاً بهینه در تمام صفحات عمومی

### 📁 ساختار پوشه‌ها

```text
src/
├── app/            → صفحات و routing فرانت
│   └── api/        → بک‌اند و APIها
├── public/
│   ├── img/        → عکس‌های سایت
│   └── font/       → فونت‌های سایت
├── controllers/    → responseهای HTTP
├── services/       → کل منطق کسب‌وکار
├── components/     → UI و استایل (auth، theme، layout، ui)
└── utils/          → کتابخانه‌ها، real-time، ابزارها
.env                → اسرار: کلید توکن‌ها، آدرس دیتابیس (هرگز کامیت نشود!)
```

### 📖 نحوه‌ی باز کردن کانواز

1. [Obsidian](https://obsidian.md) رایگان را نصب کنید و این پوشه را به‌عنوان vault باز کنید
2. روی `Security-Blueprint.canvas` کلیک کنید
3. گروه‌های شماره‌دار و فلش‌ها را دنبال کنید (۱ تا ۶)

اوبسیدین ندارید؟ هر برنامه‌ای که از استاندارد باز [JSON Canvas](https://jsoncanvas.org) پشتیبانی کند می‌تواند فایل را بخواند.

</div>

---

<div align="center">

**🔐 Built with security in mind · ساخته‌شده با نگاه امنیتی**

</div>
