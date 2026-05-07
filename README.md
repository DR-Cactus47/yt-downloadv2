# 🎬 Enhanced YouTube Downloader | دانلودر پیشرفته یوتیوب

<div align="center">

![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![yt-dlp](https://img.shields.io/badge/yt--dlp-red?style=for-the-badge)
![ffmpeg](https://img.shields.io/badge/ffmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)

**Download YouTube videos automatically using GitHub Actions**

**دانلود خودکار ویدیوهای یوتیوب با GitHub Actions**

</div>

---

## 📖 Table of Contents | فهرست مطالب

- [English Guide](#english-guide)
  - [Features](#features)
  - [How to Fork and Setup](#how-to-fork-and-setup)
  - [How to Use the Downloader Workflow](#how-to-use-the-downloader-workflow)
  - [Downloader Inputs](#downloader-inputs)
  - [How to Use the Cleanup Workflow](#how-to-use-the-cleanup-workflow)
  - [Examples](#examples)
  - [Important Notes](#important-notes)
- [راهنمای فارسی](#راهنمای-فارسی)
  - [ویژگی‌ها](#ویژگیها)
  - [نحوه فورک و راه‌اندازی](#نحوه-فورک-و-راهاندازی)
  - [نحوه استفاده از ورک‌فلو دانلودر](#نحوه-استفاده-از-ورکفلو-دانلودر)
  - [ورودی‌های دانلودر](#ورودیهای-دانلودر)
  - [نحوه استفاده از ورک‌فلو پاکسازی](#نحوه-استفاده-از-ورکفلو-پاکسازی)
  - [مثال‌ها](#مثالها)
  - [نکات مهم](#نکات-مهم)

---

# English Guide

## Features

- Download one or multiple YouTube links
- Supports videos and playlists
- Choose quality: `best`, `1080`, `720`, `480`, `audio`
- Organize files by:
  - `channel`
  - `date`
  - `playlist`
  - `flat`
- Split large files automatically
- Cache apt and pip dependencies for faster runs
- Uses Cloudflare WARP for better connectivity
- Automatically commits downloaded files into the repository
- Includes a cleanup workflow to remove old downloads

---

## How to Fork and Setup

### 1. Fork this repository
Click the **Fork** button at the top-right of this repository.

This will create your own copy of the project in your GitHub account.

---

### 2. Open your forked repository
After forking, open your own repository.

Example:
```text
https://github.com/YOUR_USERNAME/REPOSITORY_NAME

---

### 3. Enable GitHub Actions
Go to the **Actions** tab.

If GitHub shows a message asking to enable workflows, click:

text
I understand my workflows, go ahead and enable them

---

### 4. Give workflow write permissions
Go to:

text
Settings → Actions → General

Scroll to **Workflow permissions** and select:

text
Read and write permissions

Then click **Save**.

This is required because the workflow commits downloaded files back to your repository.

---

### 5. Make sure workflow files exist
Your repository should contain these files:

text
.github/workflows/youtube-downloader.yml
.github/workflows/cleanup-downloads.yml

---

## How to Use the Downloader Workflow

### Step 1
Go to the **Actions** tab.

### Step 2
From the left side, click:

text
🎬 Enhanced YouTube Downloader

### Step 3
Click the **Run workflow** button.

### Step 4
Fill in the inputs.

### Step 5
Click **Run workflow** again to start.

### Step 6
Wait for the workflow to finish.

### Step 7
After it completes, your downloaded files will be stored in:

text
downloads/

inside your repository.

---

## Downloader Inputs

### `youtube_urls`
Enter one or more YouTube links.

You can paste:
- one link per line
- or multiple links separated by commas

Example:

text
https://www.youtube.com/watch?v=video1
https://www.youtube.com/watch?v=video2

or

text
https://www.youtube.com/watch?v=video1,https://www.youtube.com/watch?v=video2

---

### `quality`
Choose one of these:

- `best`
- `1080`
- `720`
- `480`
- `audio`

#### Meaning
- `best` = best available quality
- `1080` = Full HD
- `720` = HD
- `480` = lower size video
- `audio` = audio only

---

### `split_threshold_mb`
If a downloaded file is larger than this size, it will be split automatically.

Example:

text
90

- Default is usually `90`
- Set `0` to disable splitting

---

### `organize_by`
Choose how files should be organized:

- `channel`
- `date`
- `playlist`
- `flat`

#### Example output

If `channel`:
text
downloads/Channel Name/video title.mp4

If `date`:
text
downloads/2026-05-07/video title.mp4

If `playlist`:
text
downloads/Playlist Name/01 - video title.mp4

If `flat`:
text
downloads/video title.mp4

---

### `playlist_mode`
Choose how playlist links should be handled:

- `all`
- `first_10`
- `first_5`
- `single_only`

#### Meaning
- `all` = download the full playlist
- `first_10` = only first 10 videos
- `first_5` = only first 5 videos
- `single_only` = ignore playlist and only process a single item when possible

---

## How to Use the Cleanup Workflow

If you want to remove downloaded files, use the cleanup workflow.

### Step 1
Go to the **Actions** tab.

### Step 2
Click:

text
🗑️ Clean Downloaded Videos

### Step 3
Click **Run workflow**

### Step 4
Fill the confirmation field with:

text
DELETE

This is required for safety.

### Step 5
Choose a delete mode.

### Delete modes

- `all` → remove everything in `downloads/`
- `videos_only` → remove only video files
- `audio_only` → remove only audio files
- `by_channel` → remove files from a specific channel
- `by_date` → remove files for a specific date folder

If you choose:

- `by_channel`, also fill `channel_name`
- `by_date`, also fill `date_filter` using format:

text
YYYY-MM-DD

Example:

text
2026-05-07

---

## Examples

### Download two videos in 720p

#### Inputs
text
youtube_urls:
https://www.youtube.com/watch?v=abc
https://www.youtube.com/watch?v=def

quality: 720
split_threshold_mb: 90
organize_by: channel
playlist_mode: single_only

---

### Download audio only

#### Inputs
text
youtube_urls:
https://www.youtube.com/watch?v=abc

quality: audio
organize_by: flat
playlist_mode: single_only

---

### Download full playlist

#### Inputs
text
youtube_urls:
https://www.youtube.com/playlist?list=PLxxxxxx

quality: best
organize_by: playlist
playlist_mode: all

---

### Delete only audio files

#### Cleanup inputs
text
confirmation: DELETE
delete_mode: audio_only

---

### Delete files for a specific date

#### Cleanup inputs
text
confirmation: DELETE
delete_mode: by_date
date_filter: 2026-05-07

---

## Important Notes

- The first workflow run may take longer because dependencies are installed
- Later runs are faster because apt and pip caches are used
- Large numbers of downloaded files may make the repository heavy
- Splitting helps avoid GitHub file size problems
- Downloaded files are committed into your repository history
- Cleanup workflow also creates a commit after deleting files

---

## Project Structure

text
.github/
  workflows/
youtube-downloader.yml
cleanup-downloads.yml

downloads/
README.md

---

## Tools Used

- GitHub Actions
- Python
- `yt-dlp`
- `ffmpeg`
- Cloudflare WARP

---

## Warning

Use this project responsibly and only for content you are allowed to access, download, and store. Make sure your usage follows the relevant platform rules and applicable laws.

---

# راهنمای فارسی

## ویژگی‌ها

- دانلود یک یا چند لینک یوتیوب
- پشتیبانی از ویدیو و پلی‌لیست
- انتخاب کیفیت: `best`، `1080`، `720`، `480`، `audio`
- دسته‌بندی فایل‌ها بر اساس:
  - `channel`
  - `date`
  - `playlist`
  - `flat`
- تقسیم خودکار فایل‌های بزرگ
- استفاده از کش برای افزایش سرعت اجراهای بعدی
- استفاده از Cloudflare WARP برای اتصال بهتر
- ثبت خودکار فایل‌های دانلود شده داخل ریپازیتوری
- داشتن ورک‌فلو جدا برای پاکسازی دانلودها

---

## نحوه فورک و راه‌اندازی

### 1. فورک کردن پروژه
در بالای صفحه این ریپازیتوری، روی دکمه **Fork** کلیک کنید.

با این کار یک کپی از پروژه داخل اکانت GitHub شما ساخته می‌شود.

---

### 2. وارد ریپازیتوری فورک‌شده خودتان شوید
بعد از فورک، وارد ریپازیتوری خودتان شوید.

مثال:

text
https://github.com/YOUR_USERNAME/REPOSITORY_NAME

---

### 3. فعال کردن GitHub Actions
به تب **Actions** بروید.

اگر GitHub پیامی برای فعال‌سازی ورک‌فلوها نشان داد، روی این گزینه کلیک کنید:

text
I understand my workflows, go ahead and enable them

---

### 4. دادن دسترسی نوشتن به ورک‌فلو
به مسیر زیر بروید:

text
Settings → Actions → General

در بخش **Workflow permissions** گزینه زیر را انتخاب کنید:

text
Read and write permissions

سپس روی **Save** بزنید.

این کار لازم است چون ورک‌فلو فایل‌های دانلود شده را داخل ریپازیتوری شما commit می‌کند.

---

### 5. مطمئن شوید فایل‌های ورک‌فلو وجود دارند
باید این فایل‌ها داخل ریپازیتوری شما باشند:

text
.github/workflows/youtube-downloader.yml
.github/workflows/cleanup-downloads.yml

---

## نحوه استفاده از ورک‌فلو دانلودر

### مرحله 1
به تب **Actions** بروید.

### مرحله 2
از سمت چپ این ورک‌فلو را انتخاب کنید:

text
🎬 Enhanced YouTube Downloader

### مرحله 3
روی دکمه **Run workflow** کلیک کنید.

### مرحله 4
ورودی‌ها را پر کنید.

### مرحله 5
دوباره روی **Run workflow** بزنید تا اجرا شروع شود.

### مرحله 6
صبر کنید تا اجرا کامل شود.

### مرحله 7
بعد از اتمام، فایل‌های دانلود شده داخل مسیر زیر قرار می‌گیرند:

text
downloads/

---

## ورودی‌های دانلودر

### `youtube_urls`
یک یا چند لینک یوتیوب را وارد کنید.

می‌توانید:
- هر لینک را در یک خط جدا قرار دهید
- یا چند لینک را با ویرگول جدا کنید

مثال:

text
https://www.youtube.com/watch?v=video1
https://www.youtube.com/watch?v=video2

یا

text
https://www.youtube.com/watch?v=video1,https://www.youtube.com/watch?v=video2

---

### `quality`
یکی از این گزینه‌ها را انتخاب کنید:

- `best`
- `1080`
- `720`
- `480`
- `audio`

#### معنی گزینه‌ها
- `best` = بهترین کیفیت موجود
- `1080` = فول اچ‌دی
- `720` = اچ‌دی
- `480` = کیفیت پایین‌تر با حجم کمتر
- `audio` = فقط صدا

---

### `split_threshold_mb`
اگر حجم فایل دانلود شده از این مقدار بیشتر باشد، فایل به‌صورت خودکار تقسیم می‌شود.

مثال:

text
90

- مقدار پیش‌فرض معمولاً `90` است
- برای غیرفعال کردن تقسیم، مقدار `0` بگذارید

---

### `organize_by`
مشخص می‌کند فایل‌ها چگونه دسته‌بندی شوند:

- `channel`
- `date`
- `playlist`
- `flat`

#### نمونه خروجی

اگر `channel` باشد:
text
downloads/نام کانال/نام ویدیو.mp4

اگر `date` باشد:
text
downloads/2026-05-07/نام ویدیو.mp4

اگر `playlist` باشد:
text
downloads/نام پلی‌لیست/01 - نام ویدیو.mp4

اگر `flat` باشد:
text
downloads/نام ویدیو.mp4

---

### `playlist_mode`
نحوه برخورد با لینک پلی‌لیست را مشخص می‌کند:

- `all`
- `first_10`
- `first_5`
- `single_only`

#### معنی گزینه‌ها
- `all` = دانلود کامل پلی‌لیست
- `first_10` = فقط 10 ویدیوی اول
- `first_5` = فقط 5 ویدیوی اول
- `single_only` = در صورت امکان فقط یک آیتم دانلود شود

---

## نحوه استفاده از ورک‌فلو پاکسازی

اگر خواستید فایل‌های دانلود شده را حذف کنید، از ورک‌فلو پاکسازی استفاده کنید.

### مرحله 1
به تب **Actions** بروید.

### مرحله 2
این ورک‌فلو را انتخاب کنید:

text
🗑️ Clean Downloaded Videos

### مرحله 3
روی **Run workflow** کلیک کنید.

### مرحله 4
در فیلد تأیید، دقیقاً این عبارت را وارد کنید:

text
DELETE

این مرحله برای امنیت اضافه شده است.

### مرحله 5
حالت حذف را انتخاب کنید.

### حالت‌های حذف

- `all` ← حذف همه چیز داخل `downloads/`
- `videos_only` ← حذف فقط فایل‌های ویدیویی
- `audio_only` ← حذف فقط فایل‌های صوتی
- `by_channel` ← حذف فایل‌های مربوط به یک کانال خاص
- `by_date` ← حذف فایل‌های مربوط به یک تاریخ خاص

اگر انتخاب کنید:

- `by_channel`، باید `channel_name` را هم وارد کنید
- `by_date`، باید `date_filter` را با فرمت زیر وارد کنید:

text
YYYY-MM-DD

مثال:

text
2026-05-07

---

## مثال‌ها

### دانلود دو ویدیو با کیفیت 720

#### ورودی‌ها
text
youtube_urls:
https://www.youtube.com/watch?v=abc
https://www.youtube.com/watch?v=def

quality: 720
split_threshold_mb: 90
organize_by: channel
playlist_mode: single_only

---

### دانلود فقط صدا

#### ورودی‌ها
text
youtube_urls:
https://www.youtube.com/watch?v=abc

quality: audio
organize_by: flat
playlist_mode: single_only

---

### دانلود کامل یک پلی‌لیست

#### ورودی‌ها
text
youtube_urls:
https://www.youtube.com/playlist?list=PLxxxxxx

quality: best
organize_by: playlist
playlist_mode: all

---

### حذف فقط فایل‌های صوتی

#### ورودی‌های پاکسازی
text
confirmation: DELETE
delete_mode: audio_only

---

### حذف فایل‌های یک تاریخ مشخص

#### ورودی‌های پاکسازی
text
confirmation: DELETE
delete_mode: by_date
date_filter: 2026-05-07

---

## نکات مهم

- اولین اجرا ممکن است طولانی‌تر باشد چون وابستگی‌ها نصب می‌شوند
- اجراهای بعدی به خاطر کش سریع‌تر می‌شوند
- زیاد شدن تعداد فایل‌های دانلود شده ممکن است ریپازیتوری را سنگین کند
- تقسیم فایل‌ها به جلوگیری از مشکل محدودیت حجم GitHub کمک می‌کند
- فایل‌های دانلود شده داخل تاریخچه ریپازیتوری commit می‌شوند
- ورک‌فلو پاکسازی هم بعد از حذف فایل‌ها یک commit جدید ثبت می‌کند

---

## ساختار پروژه

text
.github/
  workflows/
youtube-downloader.yml
cleanup-downloads.yml

downloads/
README.md

---

## ابزارهای استفاده‌شده

- GitHub Actions
- Python
- `yt-dlp`
- `ffmpeg`
- Cloudflare WARP

---

## هشدار

لطفاً از این پروژه به‌صورت مسئولانه استفاده کنید و فقط برای محتوایی که اجازه دسترسی، دانلود و ذخیره آن را دارید از آن استفاده نمایید. همچنین مطمئن شوید استفاده شما با قوانین پلتفرم و قوانین مربوطه سازگار باشد.
