<div align="center">

![new-api](/web/public/logo.png)

# New API

🍥 **سیستم مدیریت دروازه و دارایی‌های هوش مصنوعی نسل جدید**

<p align="center">
  <a href="./README.md">中文</a> | 
  <a href="./README.en.md">English</a> | 
  <a href="./README.fr.md">Français</a> | 
  <a href="./README.ja.md">日本語</a> |
  <strong>فارسی</strong>
</p>

<p align="center">
  <a href="https://raw.githubusercontent.com/Calcium-Ion/new-api/main/LICENSE">
    <img src="https://img.shields.io/github/license/Calcium-Ion/new-api?color=brightgreen" alt="license">
  </a>
  <a href="https://github.com/Calcium-Ion/new-api/releases/latest">
    <img src="https://img.shields.io/github/v/release/Calcium-Ion/new-api?color=brightgreen&include_prereleases" alt="release">
  </a>
  <a href="https://github.com/users/Calcium-Ion/packages/container/package/new-api">
    <img src="https://img.shields.io/badge/docker-ghcr.io-blue" alt="docker">
  </a>
  <a href="https://hub.docker.com/r/CalciumIon/new-api">
    <img src="https://img.shields.io/badge/docker-dockerHub-blue" alt="docker">
  </a>
  <a href="https://goreportcard.com/report/github.com/Calcium-Ion/new-api">
    <img src="https://goreportcard.com/badge/github.com/Calcium-Ion/new-api" alt="GoReportCard">
  </a>
</p>

<p align="center">
  <a href="https://trendshift.io/repositories/8227" target="_blank">
    <img src="https://trendshift.io/api/badge/repositories/8227" alt="Calcium-Ion%2Fnew-api | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/>
  </a>
</p>

<p align="center">
  <a href="#-شروع-سریع">شروع سریع</a> •
  <a href="#-ویژگی‌های-اصلی">ویژگی‌های اصلی</a> •
  <a href="#-استقرار">استقرار</a> •
  <a href="#-مستندات">مستندات</a> •
  <a href="#-پشتیبانی">پشتیبانی</a>
</p>

</div>

## 📝 توضیحات پروژه

> [!NOTE]  
> این پروژه یک پروژه متن‌باز است که بر اساس [One API](https://github.com/songquanpeng/one-api) توسعه داده شده است

> [!IMPORTANT]  
> - این پروژه فقط برای یادگیری شخصی است، بدون تضمین پایداری و پشتیبانی فنی
> - کاربران باید از [شرایط استفاده](https://openai.com/policies/terms-of-use) OpenAI و **قوانین و مقررات** پیروی کنند و نباید برای اهداف غیرقانونی استفاده شود
> - طبق [《اقدامات موقت برای مدیریت خدمات هوش مصنوعی مولد》](http://www.cac.gov.cn/2023-07/13/c_1690898327029107.htm)، لطفاً هیچ خدمات هوش مصنوعی مولد ثبت‌نشده‌ای را به عموم مردم در چین ارائه ندهید

---

## 🤝 شرکای مورد اعتماد ما

<p align="center">
  <em>بدون ترتیب خاص</em>
</p>

<p align="center">
  <a href="https://www.cherry-ai.com/" target="_blank">
    <img src="./docs/images/cherry-studio.png" alt="Cherry Studio" height="80" />
  </a>
  <a href="https://bda.pku.edu.cn/" target="_blank">
    <img src="./docs/images/pku.png" alt="دانشگاه پکن" height="80" />
  </a>
  <a href="https://www.compshare.cn/?ytag=GPU_yy_gh_newapi" target="_blank">
    <img src="./docs/images/ucloud.png" alt="UCloud" height="80" />
  </a>
  <a href="https://www.aliyun.com/" target="_blank">
    <img src="./docs/images/aliyun.png" alt="علی‌بابا کلود" height="80" />
  </a>
  <a href="https://io.net/" target="_blank">
    <img src="./docs/images/io-net.png" alt="IO.NET" height="80" />
  </a>
</p>

---

## 🙏 تشکر ویژه

<p align="center">
  <a href="https://www.jetbrains.com/?from=new-api" target="_blank">
    <img src="https://resources.jetbrains.com/storage/products/company/brand/logos/jb_beam.png" alt="JetBrains Logo" width="120" />
  </a>
</p>

<p align="center">
  <strong>با تشکر از <a href="https://www.jetbrains.com/?from=new-api">JetBrains</a> برای ارائه مجوز توسعه متن‌باز رایگان برای این پروژه</strong>
</p>

---

## 🚀 شروع سریع

### استفاده از Docker Compose (توصیه می‌شود)

```bash
# کلون کردن پروژه
git clone https://github.com/QuantumNous/new-api.git
cd new-api

# ویرایش پیکربندی docker-compose.yml
nano docker-compose.yml

# شروع سرویس
docker-compose up -d
```

<details>
<summary><strong>استفاده از دستورات Docker</strong></summary>

```bash
# دریافت آخرین نسخه image
docker pull calciumion/new-api:latest

# استفاده از SQLite (پیش‌فرض)
docker run --name new-api -d --restart always \
  -p 3000:3000 \
  -e TZ=Asia/Shanghai \
  -v ./data:/data \
  calciumion/new-api:latest

# استفاده از MySQL
docker run --name new-api -d --restart always \
  -p 3000:3000 \
  -e SQL_DSN="root:123456@tcp(localhost:3306)/oneapi" \
  -e TZ=Asia/Shanghai \
  -v ./data:/data \
  calciumion/new-api:latest
```

> **💡 نکته:** `-v ./data:/data` داده‌ها را در پوشه `data` دایرکتوری فعلی ذخیره می‌کند، می‌توانید آن را به مسیر مطلق مانند `-v /your/custom/path:/data` تغییر دهید

</details>

---

🎉 پس از تکمیل استقرار، برای استفاده به `http://localhost:3000` مراجعه کنید!

📖 برای روش‌های بیشتر استقرار، لطفاً به [راهنمای استقرار](https://docs.newapi.pro/zh/docs/installation) مراجعه کنید

---

## 📚 مستندات

<div align="center">

### 📖 [مستندات رسمی](https://docs.newapi.pro/zh/docs) | [![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/QuantumNous/new-api)

</div>

**راهنمای سریع:**

| دسته‌بندی | لینک |
|------|------|
| 🚀 راهنمای استقرار | [مستندات نصب](https://docs.newapi.pro/zh/docs/installation) |
| ⚙️ پیکربندی محیط | [متغیرهای محیطی](https://docs.newapi.pro/zh/docs/installation/config-maintenance/environment-variables) |
| 📡 مستندات API | [مستندات API](https://docs.newapi.pro/zh/docs/api) |
| ❓ سوالات متداول | [FAQ](https://docs.newapi.pro/zh/docs/support/faq) |
| 💬 تعامل جامعه | [کانال‌های ارتباطی](https://docs.newapi.pro/zh/docs/support/community-interaction) |

---

## ✨ ویژگی‌های اصلی

> برای ویژگی‌های دقیق لطفاً به [معرفی ویژگی‌ها](https://docs.newapi.pro/zh/docs/guide/wiki/basic-concepts/features-introduction) مراجعه کنید

### 🎨 عملکردهای اصلی

| ویژگی | توضیحات |
|------|------|
| 🎨 رابط کاربری جدید | طراحی رابط کاربری مدرن |
| 🌍 چند زبانه | پشتیبانی از چینی، انگلیسی، فرانسوی، ژاپنی |
| 🔄 سازگاری داده | کاملاً سازگار با پایگاه داده One API اصلی |
| 📈 داشبورد داده | کنسول بصری و تجزیه و تحلیل آماری |
| 🔒 مدیریت مجوزها | گروه‌بندی توکن، محدودیت مدل، مدیریت کاربر |

### 💰 پرداخت و صورتحساب

- ✅ شارژ آنلاین (EPay، Stripe)
- ✅ قیمت‌گذاری مدل بر اساس تعداد
- ✅ پشتیبانی از صورتحساب کش (OpenAI، Azure، DeepSeek، Claude، Qwen و تمام مدل‌های پشتیبانی شده)
- ✅ پیکربندی سیاست صورتحساب انعطاف‌پذیر

### 🔐 احراز هویت و امنیت

- 😈 ورود با احراز هویت Discord
- 🤖 ورود با احراز هویت LinuxDO
- 📱 ورود با احراز هویت Telegram
- 🔑 احراز هویت یکپارچه OIDC
- 🔍 جستجوی کلید برای استفاده از سهمیه (با [neko-api-key-tool](https://github.com/Calcium-Ion/neko-api-key-tool))

### 🚀 ویژگی‌های پیشرفته

**پشتیبانی از فرمت API:**
- ⚡ [OpenAI Responses](https://docs.newapi.pro/zh/docs/api/ai-model/chat/openai/create-response)
- ⚡ [OpenAI Realtime API](https://docs.newapi.pro/zh/docs/api/ai-model/realtime/create-realtime-session) (شامل Azure)
- ⚡ [Claude Messages](https://docs.newapi.pro/zh/docs/api/ai-model/chat/create-message)
- ⚡ [Google Gemini](https://doc.newapi.pro/api/google-gemini-chat)
- 🔄 [مدل‌های Rerank](https://docs.newapi.pro/zh/docs/api/ai-model/rerank/create-rerank) (Cohere، Jina)

**مسیریابی هوشمند:**
- ⚖️ تصادفی وزنی کانال
- 🔄 تلاش مجدد خودکار در صورت شکست
- 🚦 محدودیت نرخ مدل در سطح کاربر

**تبدیل فرمت:**
- 🔄 **OpenAI Compatible ⇄ Claude Messages**
- 🔄 **OpenAI Compatible → Google Gemini**
- 🔄 **Google Gemini → OpenAI Compatible** - فقط متن، فراخوانی تابع هنوز پشتیبانی نمی‌شود
- 🚧 **OpenAI Compatible ⇄ OpenAI Responses** - در حال توسعه
- 🔄 **عملکرد تبدیل تفکر به محتوا**

**پشتیبانی Reasoning Effort:**

<details>
<summary>مشاهده پیکربندی دقیق</summary>

**مدل‌های سری OpenAI:**
- `o3-mini-high` - تلاش استدلال بالا
- `o3-mini-medium` - تلاش استدلال متوسط
- `o3-mini-low` - تلاش استدلال پایین
- `gpt-5-high` - تلاش استدلال بالا
- `gpt-5-medium` - تلاش استدلال متوسط
- `gpt-5-low` - تلاش استدلال پایین

**مدل‌های تفکر Claude:**
- `claude-3-7-sonnet-20250219-thinking` - فعال‌سازی حالت تفکر

**مدل‌های سری Google Gemini:**
- `gemini-2.5-flash-thinking` - فعال‌سازی حالت تفکر
- `gemini-2.5-flash-nothinking` - غیرفعال‌سازی حالت تفکر
- `gemini-2.5-pro-thinking` - فعال‌سازی حالت تفکر
- `gemini-2.5-pro-thinking-128` - فعال‌سازی حالت تفکر با بودجه تفکر 128 توکن
- همچنین می‌توانید `-low` / `-medium` / `-high` را مستقیماً به نام مدل Gemini اضافه کنید تا شدت تفکر را کنترل کنید (نیازی به تنظیم پسوند بودجه تفکر نیست)

</details>

---

## 🤖 پشتیبانی از مدل

> برای جزئیات، لطفاً به [مستندات API - رابط رله](https://docs.newapi.pro/zh/docs/api) مراجعه کنید

| نوع مدل | توضیحات | مستندات |
|---------|------|------|
| 🤖 OpenAI GPTs | سری gpt-4-gizmo-* | - |
| 🎨 Midjourney-Proxy | [Midjourney-Proxy(Plus)](https://github.com/novicezk/midjourney-proxy) | [مستندات](https://doc.newapi.pro/api/midjourney-proxy-image) |
| 🎵 Suno-API | [Suno API](https://github.com/Suno-API/Suno-API) | [مستندات](https://doc.newapi.pro/api/suno-music) |
| 🔄 Rerank | Cohere، Jina | [مستندات](https://docs.newapi.pro/zh/docs/api/ai-model/rerank/create-rerank) |
| 💬 Claude | فرمت Messages | [مستندات](https://docs.newapi.pro/zh/docs/api/ai-model/chat/create-message) |
| 🌐 Gemini | فرمت Google Gemini | [مستندات](https://doc.newapi.pro/api/google-gemini-chat) |
| 🔧 Dify | حالت ChatFlow | - |
| 🎯 سفارشی | پشتیبانی از آدرس فراخوانی کامل | - |

### 📡 رابط‌های پشتیبانی شده

<details>
<summary>مشاهده لیست کامل رابط‌ها</summary>

- [رابط چت (Chat Completions)](https://docs.newapi.pro/zh/docs/api/ai-model/chat/openai/create-chat-completion)
- [رابط پاسخ (Responses)](https://docs.newapi.pro/zh/docs/api/ai-model/chat/openai/create-response)
- [رابط تصویر (Image)](https://docs.newapi.pro/zh/docs/api/ai-model/images/openai/v1-images-generations--post)
- [رابط صوتی (Audio)](https://docs.newapi.pro/zh/docs/api/ai-model/audio/openai/create-transcription)
- [رابط ویدئو (Video)](https://docs.newapi.pro/zh/docs/api/ai-model/videos/create-video-generation)
- [رابط جاسازی (Embeddings)](https://docs.newapi.pro/zh/docs/api/ai-model/embeddings/create-embedding)
- [رابط مرتب‌سازی مجدد (Rerank)](https://docs.newapi.pro/zh/docs/api/ai-model/rerank/create-rerank)
- [گفتگوی بلادرنگ (Realtime)](https://docs.newapi.pro/zh/docs/api/ai-model/realtime/create-realtime-session)
- [چت Claude](https://docs.newapi.pro/zh/docs/api/ai-model/chat/create-message)
- [چت Google Gemini](https://doc.newapi.pro/api/google-gemini-chat)

</details>

---

## 🚢 استقرار

> [!TIP]
> **آخرین نسخه Docker image:** `calciumion/new-api:latest`

### 📋 الزامات استقرار

| جزء | الزامات |
|------|------|
| **پایگاه داده محلی** | SQLite (Docker باید دایرکتوری `/data` را mount کند)|
| **پایگاه داده راه دور** | MySQL ≥ 5.7.8 یا PostgreSQL ≥ 9.6 |
| **موتور کانتینر** | Docker / Docker Compose |

### ⚙️ پیکربندی متغیرهای محیطی

<details>
<summary>پیکربندی متغیرهای محیطی رایج</summary>

| نام متغیر | توضیحات | مقدار پیش‌فرض |
|--------|------|--------|
| `SESSION_SECRET` | کلید جلسه (برای استقرار چند ماشینه ضروری است) | - |
| `CRYPTO_SECRET` | کلید رمزگذاری (برای Redis ضروری است) | - |
| `SQL_DSN` | رشته اتصال پایگاه داده | - |
| `REDIS_CONN_STRING` | رشته اتصال Redis | - |
| `STREAMING_TIMEOUT` | زمان انقضای جریان (ثانیه) | `300` |
| `STREAM_SCANNER_MAX_BUFFER_MB` | حداکثر بافر در هر خط اسکنر جریان (MB)، تولید تصویر و غیره که قطعات بسیار بزرگ `data:` (مانند تصاویر 4K base64) را باید به اندازه کافی افزایش دهید | `64` |
| `MAX_REQUEST_BODY_MB` | حداکثر اندازه بدنه درخواست (MB، **پس از باز کردن فشرده‌سازی** محاسبه می‌شود؛ از درخواست‌های بسیار بزرگ/zip bomb که باعث افزایش حافظه می‌شوند جلوگیری می‌کند)، تجاوز از آن `413` برمی‌گرداند | `32` |
| `AZURE_DEFAULT_API_VERSION` | نسخه API Azure | `2025-04-01-preview` |
| `ERROR_LOG_ENABLED` | سوئیچ لاگ خطا | `false` |
| `PYROSCOPE_URL` | آدرس سرویس Pyroscope | - |
| `PYROSCOPE_APP_NAME` | نام برنامه Pyroscope | `new-api` |
| `PYROSCOPE_BASIC_AUTH_USER` | نام کاربری احراز هویت پایه Pyroscope | - |
| `PYROSCOPE_BASIC_AUTH_PASSWORD` | رمز عبور احراز هویت پایه Pyroscope | - |
| `PYROSCOPE_MUTEX_RATE` | نرخ نمونه‌برداری mutex Pyroscope | `5` |
| `PYROSCOPE_BLOCK_RATE` | نرخ نمونه‌برداری block Pyroscope | `5` |
| `HOSTNAME` | نام میزبان در برچسب Pyroscope | `new-api` |

📖 **پیکربندی کامل:** [مستندات متغیرهای محیطی](https://docs.newapi.pro/zh/docs/installation/config-maintenance/environment-variables)

</details>

### 🔧 روش‌های استقرار

<details>
<summary><strong>روش 1: Docker Compose (توصیه می‌شود)</strong></summary>

```bash
# کلون کردن پروژه
git clone https://github.com/QuantumNous/new-api.git
cd new-api

# ویرایش پیکربندی
nano docker-compose.yml

# شروع سرویس
docker-compose up -d
```

</details>

<details>
<summary><strong>روش 2: دستورات Docker</strong></summary>

**استفاده از SQLite:**
```bash
docker run --name new-api -d --restart always \
  -p 3000:3000 \
  -e TZ=Asia/Shanghai \
  -v ./data:/data \
  calciumion/new-api:latest
```

**استفاده از MySQL:**
```bash
docker run --name new-api -d --restart always \
  -p 3000:3000 \
  -e SQL_DSN="root:123456@tcp(localhost:3306)/oneapi" \
  -e TZ=Asia/Shanghai \
  -v ./data:/data \
  calciumion/new-api:latest
```

> **💡 توضیح مسیر:** 
> - `./data:/data` - مسیر نسبی، داده‌ها در پوشه data دایرکتوری فعلی ذخیره می‌شوند
> - همچنین می‌توانید از مسیر مطلق استفاده کنید، به عنوان مثال: `/your/custom/path:/data`

</details>

<details>
<summary><strong>روش 3: پنل BaoTa</strong></summary>

1. نصب پنل BaoTa (نسخه ≥ 9.2.0)
2. جستجوی **New-API** در فروشگاه برنامه
3. نصب با یک کلیک

📖 [آموزش تصویری](./docs/BT.md)

</details>

### ⚠️ ملاحظات استقرار چند ماشینه

> [!WARNING]
> - **باید تنظیم شود** `SESSION_SECRET` - در غیر این صورت وضعیت ورود ناسازگار است
> - **Redis مشترک باید تنظیم شود** `CRYPTO_SECRET` - در غیر این صورت داده‌ها قابل رمزگشایی نیستند

### 🔄 تلاش مجدد کانال و کش

**پیکربندی تلاش مجدد:** `تنظیمات → تنظیمات عملیاتی → تنظیمات عمومی → تعداد تلاش مجدد در صورت شکست`

**پیکربندی کش:**
- `REDIS_CONN_STRING`: کش Redis (توصیه می‌شود)
- `MEMORY_CACHE_ENABLED`: کش حافظه

---

## 🔗 پروژه‌های مرتبط

### پروژه‌های upstream

| پروژه | توضیحات |
|------|------|
| [One API](https://github.com/songquanpeng/one-api) | پایه پروژه اصلی |
| [Midjourney-Proxy](https://github.com/novicezk/midjourney-proxy) | پشتیبانی از رابط Midjourney |

### ابزارهای پشتیبان

| پروژه | توضیحات |
|------|------|
| [neko-api-key-tool](https://github.com/Calcium-Ion/neko-api-key-tool) | ابزار جستجوی سهمیه کلید |
| [new-api-horizon](https://github.com/Calcium-Ion/new-api-horizon) | نسخه بهینه‌شده با کارایی بالای New API |

---

## 💬 پشتیبانی

### 📖 منابع مستندات

| منبع | لینک |
|------|------|
| 📘 سوالات متداول | [FAQ](https://docs.newapi.pro/zh/docs/support/faq) |
| 💬 تعامل جامعه | [کانال‌های ارتباطی](https://docs.newapi.pro/zh/docs/support/community-interaction) |
| 🐛 بازخورد مشکل | [بازخورد مشکل](https://docs.newapi.pro/zh/docs/support/feedback-issues) |
| 📚 مستندات کامل | [مستندات رسمی](https://docs.newapi.pro/zh/docs) |

### 🤝 راهنمای مشارکت

خوش‌آمدید به تمام اشکال مشارکت!

- 🐛 گزارش باگ‌ها
- 💡 پیشنهاد ویژگی‌های جدید
- 📝 بهبود مستندات
- 🔧 ارسال کد

---

## 🌟 تاریخچه ستاره‌ها

<div align="center">

[![Star History Chart](https://api.star-history.com/svg?repos=Calcium-Ion/new-api&type=Date)](https://star-history.com/#Calcium-Ion/new-api&Date)

</div>

---

<div align="center">

### 💖 با تشکر از استفاده از New API

اگر این پروژه برای شما مفید بود، خوشحال می‌شویم یک ⭐️ ستاره به ما بدهید!

**[مستندات رسمی](https://docs.newapi.pro/zh/docs)** • **[بازخورد مشکل](https://github.com/Calcium-Ion/new-api/issues)** • **[آخرین نسخه](https://github.com/Calcium-Ion/new-api/releases)**

<sub>ساخته شده با ❤️ توسط QuantumNous</sub>

</div>
