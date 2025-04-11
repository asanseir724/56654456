# سیستم مدیریت اشتراک تلگرام پرمیوم

[![GitHub license](https://img.shields.io/github/license/asanseir724/56654456)](https://github.com/asanseir724/56654456/blob/main/LICENSE)
[![Telegram](https://img.shields.io/badge/Telegram-Bot-blue)](https://t.me/your_bot_username)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-blue)](https://www.postgresql.org/)
[![Flask](https://img.shields.io/badge/Framework-Flask-lightgrey)](https://flask.palletsprojects.com/)

سیستم پیشرفته و یکپارچه برای مدیریت خودکار اشتراک پرمیوم تلگرام با پشتیبانی از پرداخت‌های ارز دیجیتال، پنل مدیریت جامع و API برای اتصال به سیستم‌های خارجی.

## نصب سریع 

### نصب کامل با یک دستور
```bash
sudo bash -c "$(curl -s https://raw.githubusercontent.com/asanseir724/56654456/main/full_install.sh)"
```

### نصب کامل با HTTPS (توصیه شده)
```bash
sudo bash -c "$(curl -s https://raw.githubusercontent.com/asanseir724/56654456/main/full_install_with_https.sh)"
```

![نمای کلی سیستم](https://github.com/asanseir724/56654456/raw/main/generated-icon.png)

## ویژگی‌های اصلی

### برای کاربران
- 🔐 ثبت‌نام آسان و سریع بدون نیاز به اطلاعات حساس
- 💰 پرداخت امن با ارزهای دیجیتال (TRX و ارزهای دیگر)
- 📱 رابط کاربری ساده و روان در تلگرام
- 🌐 دسترسی به اشتراک پرمیوم تلگرام بدون محدودیت جغرافیایی
- 📊 مشاهده تاریخچه سفارشات و وضعیت آن‌ها

### برای ادمین‌ها
- 📊 پنل مدیریت کامل با امکان مشاهده و مدیریت سفارشات
- 👥 مدیریت ادمین‌ها و سطوح دسترسی
- 📢 سیستم ارسال پیام‌های گروهی به کاربران
- 📝 تنظیم پلن‌های اشتراک، قیمت‌ها و توضیحات
- 🔄 تنظیم کانال‌های اطلاع‌رسانی و پشتیبانی
- 📱 کنترل تنظیمات ربات تلگرام
- 📜 سیستم لاگینگ پیشرفته برای عیب‌یابی
- 🔑 مدیریت API و ایجاد کلید دسترسی

### زیرساخت فنی
- 🔄 مکانیزم پیشرفته برای جلوگیری از پردازش‌های تکراری پیام‌ها
- 🔒 ذخیره‌سازی امن اطلاعات با رمزنگاری مناسب
- 📡 پشتیبانی از حالت‌های polling و webhook برای ربات تلگرام
- 🐳 پشتیبانی از Docker برای استقرار آسان
- 🌐 API کامل برای ادغام با سیستم‌های خارجی
- 🔄 مدیریت خودکار تراکنش‌های پرداخت با NowPayments

## نحوه نصب

### پیش‌نیازها
- Python 3.8 یا بالاتر
- PostgreSQL
- توکن ربات تلگرام (از [@BotFather](https://t.me/BotFather))
- کلید API از [NowPayments](https://nowpayments.io/) برای پردازش پرداخت‌های ارز دیجیتال

### نصب استاندارد
برای نصب این پروژه، دستورات زیر را اجرا کنید:

```bash
# کلون کردن مخزن
git clone https://github.com/asanseir724/56654456.git
cd 56654456

# اجرای اسکریپت نصب
bash install.sh
```

اسکریپت نصب به صورت خودکار تمام وابستگی‌ها را نصب می‌کند، دیتابیس را راه‌اندازی می‌کند و تنظیمات اولیه را انجام می‌دهد.

### نصب یک خطی (برای سرورهای لینوکس)
برای نصب سریع با یک دستور:

```bash
sudo bash -c "$(curl -s https://raw.githubusercontent.com/asanseir724/56654456/main/one_click_install_en.sh)"
```

### نصب با Docker
برای استفاده از Docker:

```bash
# کلون کردن مخزن
git clone https://github.com/asanseir724/56654456.git
cd 56654456

# ساخت و اجرا با Docker Compose
docker-compose up -d
```

## پیکربندی

1. فایل `.env.example` را به `.env` تغییر نام دهید و مقادیر مورد نیاز را وارد کنید:
```
TELEGRAM_BOT_TOKEN=your_bot_token
WEBHOOK_URL=https://your-domain.com/telegram_webhook
NOWPAYMENTS_API_KEY=your_nowpayments_api_key
DATABASE_URL=postgresql://username:password@localhost:5432/dbname
SESSION_SECRET=your_session_secret_key
```

2. دیتابیس را با اجرای اسکریپت زیر ایجاد کنید:
```bash
python migrate.py
```

3. حالت اجرای ربات را انتخاب کنید:
   - برای حالت polling:
     ```bash
     bash polling_mode.sh
     ```
   - برای حالت webhook:
     ```bash
     bash setup_https.sh
     ```

4. به آدرس `http://your-domain:5000/admin` بروید و با اطلاعات پیش‌فرض وارد شوید:
   - نام کاربری: `admin`
   - رمز عبور: `admin`

5. از طریق پنل مدیریت، تنظیمات لازم برای پلن‌ها، کانال‌ها و مشخصات پشتیبانی را انجام دهید.

## استفاده از API

این سیستم دارای API کامل برای ادغام با سیستم‌های خارجی است. مستندات API در آدرس `/api/docs` قابل دسترس است.

نمونه درخواست API برای ایجاد سفارش جدید:

```python
import requests

api_url = "https://your-domain.com/api/orders/create"
api_key = "your_api_key"

headers = {
    "X-API-KEY": api_key,
    "Content-Type": "application/json"
}

data = {
    "telegram_username": "user123",
    "plan_id": "premium_monthly"
}

response = requests.post(api_url, json=data, headers=headers)
print(response.json())
```

## عیب‌یابی

اگر با مشکلی مواجه شدید، می‌توانید از اسکریپت عیب‌یابی خودکار استفاده کنید:

```bash
bash troubleshoot.sh
```

همچنین می‌توانید لاگ‌های سیستم را از طریق پنل مدیریت در بخش "لاگ‌ها" مشاهده کنید.

## ساختار پروژه

```
.
├── api.py                 # پیاده‌سازی API
├── app.py                 # اپلیکیشن اصلی فلسک
├── config.py              # فایل تنظیمات
├── config_manager.py      # مدیریت تنظیمات پویا
├── debug_bot.py           # ابزار عیب‌یابی ربات
├── logging_config.py      # تنظیمات لاگینگ
├── main.py                # نقطه شروع برنامه
├── models.py              # مدل‌های دیتابیس
├── nowpayments.py         # ادغام با NowPayments
├── run_telegram_bot.py    # کد اصلی ربات تلگرام
├── set_webhook.py         # ابزار تنظیم وب‌هوک
├── templates/             # قالب‌های HTML
│   └── admin/             # قالب‌های پنل مدیریت
├── static/                # فایل‌های استاتیک
├── logs/                  # فایل‌های لاگ
└── scripts/               # اسکریپت‌های مختلف
```

## مشارکت

از مشارکت شما در بهبود این پروژه استقبال می‌کنیم. لطفاً برای مشارکت:

1. یک fork از پروژه ایجاد کنید
2. یک شاخه جدید برای ویژگی یا رفع باگ ایجاد کنید (`git checkout -b feature/amazing-feature`)
3. تغییرات خود را commit کنید (`git commit -m 'Add some amazing feature'`)
4. به شاخه اصلی push کنید (`git push origin feature/amazing-feature`)
5. یک Pull Request ایجاد کنید

## گزارش مشکلات

اگر با مشکلی مواجه شدید، لطفاً آن را در بخش Issues گیت‌هاب گزارش دهید.

## مجوز

این پروژه تحت مجوز MIT منتشر شده است - برای جزئیات بیشتر فایل LICENSE را مشاهده کنید.
