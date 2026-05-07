# 🎬 Enhanced YouTube Downloader

<div align="center">

## Download YouTube videos, playlists, and audio with GitHub Actions  
## دانلود ویدیو، پلی‌لیست و فایل صوتی یوتیوب با GitHub Actions

⭐ **Please Star this project first**  
🍴 **Then Fork it to your own GitHub account**

**اول لطفاً به پروژه Star بدهید** ⭐  
**بعد پروژه را Fork کنید** 🍴

</div>

---

## 📌 Important | مهم

### English
Before using this project:

1. **Star this repository** ⭐
2. **Fork this repository** 🍴
3. Open your forked repository
4. Enable **GitHub Actions**
5. Run the workflow and enjoy

### فارسی
قبل از استفاده از این پروژه:

1. **اول به پروژه Star بدهید** ⭐
2. **بعد پروژه را Fork کنید** 🍴
3. وارد ریپازیتوری Fork شده خودتان شوید
4. بخش **GitHub Actions** را فعال کنید
5. ورک‌فلو را اجرا کنید و استفاده کنید

---

# 🇬🇧 English Guide

## ✨ Overview

This project helps you download:

- YouTube videos
- YouTube playlists
- Audio only files
- Different qualities like `best`, `1080`, `720`, `480`
- Organized output by channel, date, playlist, or flat structure
- Automatic splitting of large files
- Easy cleanup workflow for downloaded files

Everything works directly through **GitHub Actions**.  
No need for a VPS or manual server setup.

---

## 🚀 How to Use

### 1. Star and Fork

First:

- Click **Star** ⭐
- Click **Fork** 🍴

After that, open your forked repository.

---

### 2. Enable Actions

Go to the **Actions** tab in your fork.

If GitHub asks for permission, enable workflows.

---

### 3. Run the Downloader Workflow

Go to:

**Actions** → **🎬 Enhanced YouTube Downloader**

Click:

**Run workflow**

Then fill the form.

---

## 📝 Workflow Inputs

### `youtube_urls`
Paste one or more YouTube URLs.

You can paste:

- one video URL
- multiple video URLs
- playlist URLs

Use **one per line** for best results.

Example:
```txt
https://www.youtube.com/watch?v=xxxxxxx
https://www.youtube.com/watch?v=yyyyyyy
https://www.youtube.com/playlist?list=zzzzzzz

---

### `quality`

Available options:

- `best` → best available quality
- `1080` → maximum $1080p$
- `720` → maximum $720p$
- `480` → maximum $480p$
- `audio` → audio only as MP3

---

### `split_threshold_mb`

If a file becomes larger than this size, it will be split automatically.

Example:

- `90` → split files larger than $90$ MB
- `0` → disable splitting

---

### `organize_by`

How downloaded files are organized:

- `channel` → create folders by channel/uploader
- `date` → create folders by upload date
- `playlist` → create folders by playlist
- `flat` → keep everything in one folder

---

### `playlist_mode`

How playlist links should be handled:

- `all` → download whole playlist
- `first_10` → first $10$ items only
- `first_5` → first $5$ items only
- `single_only` → ignore playlist and download only single item

---

## 📂 Output Location

Downloaded files are saved inside:

txt
downloads/

Depending on your selected organization mode, files may look like this:

### By channel
txt
downloads/Channel Name/video title - www.avasam.ir - .mp4

### By date
txt
downloads/2026-05-07/video title - www.avasam.ir - .mp4

### By playlist
txt
downloads/Playlist Name/1 - video title - www.avasam.ir - .mp4

### Flat
txt
downloads/video title - www.avasam.ir - .mp4

---

## 🧹 Clean Downloaded Files

This project also includes a cleanup workflow.

Go to:

**Actions** → **🗑️ Clean Downloaded Videos**

Click:

**Run workflow**

You must type:

txt
DELETE

to confirm deletion.

---

## 🗑️ Delete Modes

### `all`
Delete everything inside `downloads`

### `videos_only`
Delete only video files such as:

- `.mp4`
- `.mkv`
- `.webm`
- `.avi`
- `.mov`

### `audio_only`
Delete only audio files such as:

- `.mp3`
- `.m4a`
- `.opus`
- `.wav`
- `.flac`

### `by_channel`
Delete files from a specific channel folder

### `by_date`
Delete files from a specific date folder

---

## 💡 Tips

- Use one URL per line
- If a playlist is large, use `first_5` or `first_10`
- For music downloads, use `audio`
- If GitHub repository size matters, use splitting and cleanup regularly
- The workflow commits downloaded files directly into your repository

---

## ⚠️ Notes

- This project uses `yt-dlp`
- `ffmpeg` is installed automatically
- Cloudflare WARP is used during the workflow setup
- Download speed and availability may vary
- Very large repositories may hit GitHub limits over time

---

## ❤️ Support

If this project helped you, please:

- **Star the repository** ⭐
- **Fork it** 🍴
- Share it with others

---

# 🇮🇷 راهنمای فارسی

## ✨ معرفی پروژه

این پروژه به شما کمک می‌کند تا با استفاده از **GitHub Actions** موارد زیر را دانلود کنید:

- ویدیوهای یوتیوب
- پلی‌لیست‌های یوتیوب
- فایل صوتی
- کیفیت‌های مختلف مثل `best` ، `1080` ، `720` ، `480`
- دسته‌بندی فایل‌ها بر اساس کانال، تاریخ، پلی‌لیست یا حالت ساده
- تقسیم خودکار فایل‌های حجیم
- پاک‌سازی آسان فایل‌های دانلود شده

همه چیز داخل گیت‌هاب انجام می‌شود و نیازی به سرور جداگانه ندارید.

---

## 🚀 آموزش استفاده

### 1. اول Star کنید و بعد Fork

ابتدا:

- روی **Star** بزنید ⭐
- سپس روی **Fork** بزنید 🍴

بعد از آن وارد ریپازیتوری Fork شده خودتان شوید.

---

### 2. فعال کردن Actions

وارد تب **Actions** شوید.

اگر گیت‌هاب از شما خواست، ورک‌فلوها را فعال کنید.

---

### 3. اجرای دانلودر

مسیر:

**Actions** → **🎬 Enhanced YouTube Downloader**

سپس روی:

**Run workflow**

کلیک کنید و فرم را پر کنید.

---

## 📝 توضیح ورودی‌ها

### `youtube_urls`
در این بخش یک یا چند لینک یوتیوب وارد کنید.

می‌توانید وارد کنید:

- لینک یک ویدیو
- چند لینک ویدیو
- لینک پلی‌لیست

بهتر است هر لینک را در **یک خط جداگانه** قرار دهید.

مثال:

txt
https://www.youtube.com/watch?v=xxxxxxx
https://www.youtube.com/watch?v=yyyyyyy
https://www.youtube.com/playlist?list=zzzzzzz

---

### `quality`

گزینه‌های کیفیت:

- `best` → بهترین کیفیت موجود
- `1080` → حداکثر $1080p$
- `720` → حداکثر $720p$
- `480` → حداکثر $480p$
- `audio` → فقط صوت با فرمت MP3

---

### `split_threshold_mb`

اگر حجم فایل از این مقدار بیشتر شود، فایل به صورت خودکار چند قسمتی می‌شود.

مثال:

- `90` → تقسیم فایل‌های بزرگ‌تر از $90$ مگابایت
- `0` → غیرفعال کردن تقسیم

---

### `organize_by`

نحوه دسته‌بندی فایل‌ها:

- `channel` → بر اساس نام کانال
- `date` → بر اساس تاریخ انتشار
- `playlist` → بر اساس نام پلی‌لیست
- `flat` → همه فایل‌ها در یک پوشه

---

### `playlist_mode`

نحوه رفتار با لینک پلی‌لیست:

- `all` → دانلود کامل پلی‌لیست
- `first_10` → فقط $10$ آیتم اول
- `first_5` → فقط $5$ آیتم اول
- `single_only` → فقط یک ویدیو دانلود شود و پلی‌لیست نادیده گرفته شود

---

## 📂 محل ذخیره فایل‌ها

فایل‌های دانلود شده داخل پوشه زیر ذخیره می‌شوند:

txt
downloads/

بسته به نوع دسته‌بندی، ساختار فایل‌ها می‌تواند شبیه این باشد:

### بر اساس کانال
txt
downloads/Channel Name/video title - www.avasam.ir - .mp4

### بر اساس تاریخ
txt
downloads/2026-05-07/video title - www.avasam.ir - .mp4

### بر اساس پلی‌لیست
txt
downloads/Playlist Name/1 - video title - www.avasam.ir - .mp4

### حالت ساده
txt
downloads/video title - www.avasam.ir - .mp4

---

## 🧹 پاک کردن فایل‌های دانلود شده

برای حذف فایل‌ها، از ورک‌فلو پاک‌سازی استفاده کنید.

مسیر:

**Actions** → **🗑️ Clean Downloaded Videos**

روی:

**Run workflow**

کلیک کنید.

برای تأیید حذف، باید دقیقاً این عبارت را وارد کنید:

txt
DELETE

---

## 🗑️ حالت‌های حذف

### `all`
حذف همه فایل‌های داخل پوشه `downloads`

### `videos_only`
فقط فایل‌های ویدیویی حذف می‌شوند، مثل:

- `.mp4`
- `.mkv`
- `.webm`
- `.avi`
- `.mov`

### `audio_only`
فقط فایل‌های صوتی حذف می‌شوند، مثل:

- `.mp3`
- `.m4a`
- `.opus`
- `.wav`
- `.flac`

### `by_channel`
حذف فایل‌های مربوط به یک کانال خاص

### `by_date`
حذف فایل‌های مربوط به یک تاریخ خاص

---

## 💡 نکات مهم

- بهتر است هر لینک را در یک خط جداگانه وارد کنید
- اگر پلی‌لیست طولانی است، از `first_5` یا `first_10` استفاده کنید
- برای دانلود موزیک، گزینه `audio` مناسب‌تر است
- اگر حجم ریپازیتوری برایتان مهم است، مرتب فایل‌ها را پاک‌سازی کنید
- فایل‌های دانلود شده مستقیماً داخل ریپازیتوری شما commit می‌شوند

---

## ⚠️ توجه

- این پروژه از `yt-dlp` استفاده می‌کند
- `ffmpeg` به‌صورت خودکار نصب می‌شود
- در فرایند اجرا، Cloudflare WARP هم تنظیم می‌شود
- سرعت دانلود و دسترسی ممکن است بسته به شرایط متفاوت باشد
- اگر فایل‌های خیلی زیادی ذخیره کنید، ممکن است به محدودیت‌های گیت‌هاب نزدیک شوید

---

## ❤️ حمایت

اگر این پروژه برای شما مفید بود:

- به پروژه **Star** بدهید ⭐
- آن را **Fork** کنید 🍴
- با دیگران به اشتراک بگذارید

---

## 📌 Suggested Workflow Order | ترتیب پیشنهادی استفاده

### English
1. Star the project ⭐  
2. Fork the project 🍴  
3. Enable Actions  
4. Run downloader workflow  
5. Check downloaded files in `downloads/`  
6. Use cleanup workflow when needed  

### فارسی
1. اول پروژه را **Star** کنید ⭐  
2. سپس پروژه را **Fork** کنید 🍴  
3. بخش Actions را فعال کنید  
4. ورک‌فلو دانلود را اجرا کنید  
5. فایل‌ها را داخل `downloads/` بررسی کنید  
6. در صورت نیاز از ورک‌فلو پاک‌سازی استفاده کنید  

---

<div align="center">

## ⭐ Star First — Fork Next — Enjoy

## ⭐ اول Star — بعد Fork — سپس استفاده

</div>


If you want, I can also make it:
1. **more professional**
2. **more stylish with badges and screenshots section**
3. **ready with your exact GitHub username/repo links**
