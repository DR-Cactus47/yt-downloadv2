# 🎬 Enhanced YouTube Downloader
## دانلودر پیشرفته یوتیوب با GitHub Actions

A powerful GitHub Actions based workflow for downloading YouTube videos, playlists, and audio files automatically, organizing them neatly, splitting large files, and pushing them back to your repository.

یک ورک‌فلو قدرتمند بر پایه GitHub Actions برای دانلود ویدیوها، پلی‌لیست‌ها و فایل‌های صوتی یوتیوب به‌صورت خودکار، با قابلیت دسته‌بندی، تقسیم فایل‌های بزرگ، و ذخیره در ریپازیتوری.

---

# 📌 Features | ویژگی‌ها

## English
- Download one or multiple YouTube URLs
- Supports videos and playlists
- Choose quality: `best`, `1080`, `720`, `480`, `audio`
- Organize downloads by:
  - channel
  - date
  - playlist
  - flat
- Split large files automatically
- Cleanup workflow for removing downloaded files
- Uses caching for faster installs
- Uses Cloudflare WARP for better connectivity

## فارسی
- دانلود یک یا چند لینک یوتیوب
- پشتیبانی از ویدیو و پلی‌لیست
- انتخاب کیفیت: `best`، `1080`، `720`، `480`، `audio`
- دسته‌بندی فایل‌ها بر اساس:
  - کانال
  - تاریخ
  - پلی‌لیست
  - بدون دسته‌بندی
- تقسیم خودکار فایل‌های بزرگ
- ورک‌فلو جدا برای پاک کردن فایل‌های دانلود شده
- استفاده از کش برای افزایش سرعت نصب
- استفاده از Cloudflare WARP برای اتصال بهتر

---

# 📂 Project Structure | ساختار پروژه
```text
.github/
  workflows/
youtube-downloader.yml
cleanup-downloads.yml

downloads/

---

# 🚀 How to Use | نحوه استفاده

## English Guide

### 1. Add the workflows
Put your workflow files inside:

text
.github/workflows/

Example:
- `youtube-downloader.yml`
- `cleanup-downloads.yml`

### 2. Enable GitHub Actions permissions
Go to:

**Repository Settings → Actions → General → Workflow permissions**

Set to:

text
Read and write permissions

Then save.

### 3. Run the downloader
Go to the **Actions** tab, choose:

text
🎬 Enhanced YouTube Downloader

Click **Run workflow** and fill the fields.

---

## راهنمای فارسی

### 1. فایل‌های ورک‌فلو را اضافه کنید
فایل‌های ورک‌فلو را داخل مسیر زیر قرار دهید:

text
.github/workflows/

مثال:
- `youtube-downloader.yml`
- `cleanup-downloads.yml`

### 2. دسترسی GitHub Actions را فعال کنید
به مسیر زیر بروید:

**Settings → Actions → General → Workflow permissions**

و گزینه زیر را انتخاب کنید:

text
Read and write permissions

سپس ذخیره کنید.

### 3. اجرای دانلودر
به تب **Actions** بروید و این ورک‌فلو را انتخاب کنید:

text
🎬 Enhanced YouTube Downloader

روی **Run workflow** بزنید و فیلدها را پر کنید.

---

# 🎛 Downloader Inputs | ورودی‌های دانلودر

## 1. `youtube_urls`
### English
Paste one or more YouTube URLs. You can put each URL on a new line.

Example:

text
https://www.youtube.com/watch?v=example1
https://www.youtube.com/watch?v=example2

### فارسی
یک یا چند لینک یوتیوب را وارد کنید. هر لینک را می‌توانید در یک خط جداگانه قرار دهید.

مثال:

text
https://www.youtube.com/watch?v=example1
https://www.youtube.com/watch?v=example2

---

## 2. `quality`
### Options
- `best`
- `1080`
- `720`
- `480`
- `audio`

### English
Select download quality.

### فارسی
کیفیت دانلود را انتخاب کنید.

---

## 3. `split_threshold_mb`
### English
If a file is larger than this size, it will be split automatically into zip parts.

- Default: `90`
- Use `0` to disable splitting

### فارسی
اگر حجم فایل از این مقدار بیشتر باشد، فایل به‌صورت خودکار به چند قسمت zip تقسیم می‌شود.

- مقدار پیش‌فرض: `90`
- برای غیرفعال کردن تقسیم: `0`

---

## 4. `organize_by`
### Options
- `channel`
- `date`
- `playlist`
- `flat`

### English
Controls how downloaded files are organized.

### فارسی
مشخص می‌کند فایل‌ها چطور دسته‌بندی شوند.

---

## 5. `playlist_mode`
### Options
- `all`
- `first_10`
- `first_5`
- `single_only`

### English
Controls playlist behavior.

### فارسی
مشخص می‌کند پلی‌لیست‌ها چگونه دانلود شوند.

---

# 📁 Output Structure | ساختار فایل‌های خروجی

## English
Depending on `organize_by`, files will be saved differently.

### By channel
text
downloads/Channel Name/video title.ext

### By date
text
downloads/2026-05-07/video title.ext

### By playlist
text
downloads/Playlist Name/1 - video title.ext

### Flat
text
downloads/video title.ext

## فارسی
بسته به مقدار `organize_by`، فایل‌ها به شکل‌های مختلف ذخیره می‌شوند.

### بر اساس کانال
text
downloads/نام کانال/نام ویدیو.ext

### بر اساس تاریخ
text
downloads/2026-05-07/نام ویدیو.ext

### بر اساس پلی‌لیست
text
downloads/نام پلی‌لیست/1 - نام ویدیو.ext

### بدون دسته‌بندی
text
downloads/نام ویدیو.ext

---

# 🧹 Cleanup Workflow | ورک‌فلو پاکسازی

## English
To remove downloaded files, run:

text
🗑️ Clean Downloaded Videos

You must type:

text
DELETE

in the confirmation field.

### Delete modes
- `all`
- `videos_only`
- `audio_only`
- `by_channel`
- `by_date`

If using:
- `by_channel`, enter `channel_name`
- `by_date`, enter `date_filter` in format `YYYY-MM-DD`

## فارسی
برای حذف فایل‌های دانلود شده، این ورک‌فلو را اجرا کنید:

text
🗑️ Clean Downloaded Videos

باید در قسمت تأیید، این عبارت را دقیقاً وارد کنید:

text
DELETE

### حالت‌های حذف
- `all`
- `videos_only`
- `audio_only`
- `by_channel`
- `by_date`

اگر از این موارد استفاده می‌کنید:
- برای `by_channel` باید `channel_name` وارد کنید
- برای `by_date` باید `date_filter` با فرمت `YYYY-MM-DD` وارد کنید

---

# 📝 Example Usage | مثال استفاده

## English

### Download 2 videos in 720p
- `youtube_urls`:
text
https://www.youtube.com/watch?v=abc
https://www.youtube.com/watch?v=def
- `quality`: `720`
- `split_threshold_mb`: `90`
- `organize_by`: `channel`
- `playlist_mode`: `single_only`

### Download audio only
- `quality`: `audio`

### Download first 5 videos from playlist
- `playlist_mode`: `first_5`

## فارسی

### دانلود 2 ویدیو با کیفیت 720
- `youtube_urls`:
text
https://www.youtube.com/watch?v=abc
https://www.youtube.com/watch?v=def
- `quality`: `720`
- `split_threshold_mb`: `90`
- `organize_by`: `channel`
- `playlist_mode`: `single_only`

### دانلود فقط صدا
- `quality`: `audio`

### دانلود 5 ویدیوی اول از پلی‌لیست
- `playlist_mode`: `first_5`

---

# ⚙️ Notes | نکات

## English
- First run may take longer because dependencies must be installed
- Later runs are faster thanks to cache
- Very large repositories may become slow if too many files are committed
- Splitting large files helps avoid GitHub file size issues

## فارسی
- اجرای اول ممکن است بیشتر طول بکشد چون وابستگی‌ها نصب می‌شوند
- اجرای بعدی به خاطر کش سریع‌تر خواهد بود
- اگر تعداد فایل‌های ذخیره‌شده در ریپازیتوری زیاد شود، ممکن است ریپو کند شود
- تقسیم فایل‌های بزرگ کمک می‌کند به محدودیت حجم فایل GitHub برخورد نکنید

---

# ❗ Important Warning | هشدار مهم

## English
Please use this project responsibly and only for content you are allowed to access and store. Make sure you comply with the relevant platform terms and applicable laws.

## فارسی
لطفاً از این پروژه مسئولانه استفاده کنید و فقط برای محتوایی که مجاز به دسترسی و ذخیره‌سازی آن هستید استفاده نمایید. همچنین قوانین مربوطه و شرایط استفاده پلتفرم را رعایت کنید.

---

# ❤️ Credits | سازنده

## English
Built with:
- GitHub Actions
- Python
- `yt-dlp`
- `ffmpeg`
- Cloudflare WARP

## فارسی
ساخته شده با:
- GitHub Actions
- Python
- `yt-dlp`
- `ffmpeg`
- Cloudflare WARP

---

# 📌 Suggested File Names | نام پیشنهادی فایل‌ها

text
.github/workflows/youtube-downloader.yml
.github/workflows/cleanup-downloads.yml
README.md


If you want, I can also make it:
1. **more professional**
2. **more красивый / fancy with badges and centered sections**
3. **fully RTL-styled Persian section**
4. **with screenshots section placeholders**
