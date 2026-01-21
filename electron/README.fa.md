# برنامه دسکتاپ Electron برای New API

این دایرکتوری شامل wrapper Electron برای New API است که یک برنامه دسکتاپ بومی با پشتیبانی از سینی سیستم برای Windows، macOS و Linux ارائه می‌دهد.

## پیش‌نیازها

### 1. فایل باینری Go (ضروری)
برنامه Electron نیاز به فایل باینری کامپایل شده Go دارد تا کار کند. دو گزینه دارید:

**گزینه A: استفاده از باینری موجود (بدون نصب Go)**
```bash
# اگر باینری از پیش ساخته شده دارید (به عنوان مثال، new-api-macos)
cp ../new-api-macos ../new-api
```

**گزینه B: ساخت از منبع (نیاز به Go)**
TODO

### 3. وابستگی‌های Electron
```bash
cd electron
npm install
```

## توسعه

اجرای برنامه در حالت توسعه:
```bash
npm start
```

این کار:
- بک‌اند Go را در پورت 3000 راه‌اندازی می‌کند
- یک پنجره Electron با DevTools فعال باز می‌کند
- یک آیکون سینی سیستم ایجاد می‌کند (نوار منو در macOS)
- پایگاه داده را در `../data/new-api.db` ذخیره می‌کند

## ساخت برای تولید

### ساخت سریع
```bash
# اطمینان از وجود فایل باینری Go در دایرکتوری والد
ls ../new-api  # باید وجود داشته باشد

# ساخت برای پلتفرم فعلی
npm run build

# ساخت‌های مخصوص پلتفرم
npm run build:mac    # ایجاد .dmg و .zip
npm run build:win    # ایجاد نصاب .exe
npm run build:linux  # ایجاد .AppImage و .deb
```

### خروجی ساخت
- برنامه‌های ساخته شده در `electron/dist/` هستند
- macOS: `.dmg` (نصاب) و `.zip` (قابل حمل)
- Windows: `.exe` (نصاب) و exe قابل حمل
- Linux: `.AppImage` و `.deb`

## پیکربندی

### پورت
پورت پیش‌فرض 3000 است. برای تغییر، فایل `main.js` را ویرایش کنید:
```javascript
const PORT = 3000; // تغییر به پورت مورد نظر
```

### مکان پایگاه داده
- **توسعه**: `../data/new-api.db` (دایرکتوری پروژه)
- **تولید**:
  - macOS: `~/Library/Application Support/New API/data/`
  - Windows: `%APPDATA%/New API/data/`
  - Linux: `~/.config/New API/data/`
