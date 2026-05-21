# Cinematic Scroll-Driven Portfolio

یک وبسایت پورتفولیو سینمایی با Three.js که با اسکرول کنترل می‌شود.

## ویژگی‌ها

- ✨ **Three.js Scene**: صحنه سه‌بعدی با 5 تصویر پروژه در امتداد محور Z
- 🎜 **Scroll-Driven Camera**: حرکت دوربین بر اساس اسکرول صفحه
- 🎵 **Ambient Audio System**: سیستم صوتی محیطی با crossfade بین پروژه‌ها
- 🎨 **Glassmorphism UI**: رابط کاربری شیشه‌ای مدرن
- ⚙️ **Admin Panel**: پنل مدیریت با localStorage و قابلیت export JSON
- 🚀 **Vercel Ready**: آماده deployment روی Vercel

## ساختار فایل‌ها

```
├── index.html          # صفحه اصلی با Three.js
├── admin.html          # پنل مدیریت
├── vercel.json         # تنظیمات Vercel
├── README.md           # راهنما
├── 1.png              # تصاویر پروژه‌ها
├── 2.png
├── 3.png
├── 4.png
└── 5.png
```

## نصب و راه‌اندازی محلی

1. کلون کردن یا دانلود پروژه
2. اجرای سرور محلی:

```bash
# با Python
python -m http.server 8000

# یا با Node.js
npx serve

# یا با PHP
php -S localhost:8000
```

3. باز کردن `http://localhost:8000` در مرورگر

## Deployment روی Vercel

### روش ۱: استفاده از Vercel CLI

```bash
# نصب Vercel CLI
npm i -g vercel

# لاگین به حساب Vercel
vercel login

# Deploy با تنظیمات production
vercel --prod
```

### روش ۲: استفاده از Git

1. ایجاد repository در GitHub
2. فایل‌ها را push کنید
3. در پنل Vercel، پروژه را import کنید
4. Vercel به‌طور خودکار `vercel.json` را تشخیص می‌دهد

### تنظیمات Upstash Redis (اختیاری)

برای ذخیره‌سازی server-side:

```javascript
// مثال استفاده در Edge Function
const response = await fetch("https://your-upstash-endpoint.upstash.io/set/key/val", {
  method: "POST",
  headers: {
    "Authorization": "Bearer YOUR_UPSTASH_TOKEN"
  }
});
```

## پنل مدیریت

- **URL**: `/admin.html`
- **Password پیش‌فرض**: `admin123`
- **قابلیت‌ها**:
  - ویرایش پروژه‌ها
  - تنظیم رنگ‌ها و استایل‌ها
  - تنظیمات صوتی
  - Export JSON

## تنظیمات صوتی

صوت به‌طور خودکار بعد از اولین gesture کاربر (scroll، click، keydown، یا touchstart) با تأخیر 80ms پخش می‌شود.

## تصاویر

برای بهترین عملکرد:
- نام فایل‌ها باید `1.png` تا `5.png` باشد
- فرمت توصیه شده: PNG یا WebP
- اندازه توصیه شده: 1920x1080 یا نسبت‌های مشابه

## سفارشی‌سازی

### تغییر رنگ‌ها

در `admin.html`:
1. لاگین کنید
2. بخش Settings
3. تغییر Accent Color و Background

### تغییر فاصله پروژه‌ها

در `index.html`، مقدار `zSpacing` را تغییر دهید:

```javascript
const CONFIG = {
  zSpacing: 8,  // فاصله بین پروژه‌ها
  cameraZ: 5,   // موقعیت اولیه دوربین
};
```

## پشتیبانی مرورگر

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## License

MIT License - آزاد برای استفاده شخصی و تجاری

## ساخته شده با

- Three.js
- Vanilla JavaScript
- CSS Glassmorphism
- HTML5 Audio API