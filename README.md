# 🎬 Enhanced YouTube Downloader | دانلودر پیشرفته یوتیوب

<div align="center">

![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)

**Download YouTube videos automatically using GitHub Actions - No software installation needed!**

**دانلود خودکار ویدیوهای یوتیوب با GitHub Actions - بدون نیاز به نصب نرم‌افزار!**

</div>

---

## 📋 Table of Contents | فهرست مطالب

- [English Guide](#-english-guide)
  - [Features](#-features)
  - [Step-by-Step Setup](#-step-by-step-setup)
  - [How to Download Videos](#-how-to-download-videos)
  - [How to Clean Up Downloads](#-how-to-clean-up-downloads)
  - [Input Parameters Explained](#-input-parameters-explained)
  - [Examples](#-examples)
- [راهنمای فارسی](#-راهنمای-فارسی)
  - [ویژگی‌ها](#-ویژگیها)
  - [راهنمای نصب گام‌به‌گام](#-راهنمای-نصب-گامبهگام)
  - [نحوه دانلود ویدیو](#-نحوه-دانلود-ویدیو)
  - [نحوه پاکسازی فایل‌ها](#-نحوه-پاکسازی-فایلها)
  - [توضیح پارامترهای ورودی](#-توضیح-پارامترهای-ورودی)
  - [مثال‌های کاربردی](#-مثالهای-کاربردی)

---

# 🇬🇧 English Guide

## ✨ Features

- 🎥 **Download YouTube videos** in multiple qualities (best, 1080p, 720p, 480p)
- 🎵 **Extract audio only** in MP3 format
- 📋 **Playlist support** - download entire playlists or limit to first N videos
- 📂 **Smart organization** - organize by channel, date, playlist, or flat structure
- ✂️ **Auto-split large files** - automatically split files larger than specified size
- 💾 **Intelligent caching** - faster subsequent runs with apt and pip caching
- 🌐 **Cloudflare WARP** - better connectivity and bypass restrictions
- 🔄 **Auto-commit** - downloaded files automatically pushed to your repository
- 🗑️ **Cleanup workflow** - dedicated workflow to manage and delete downloads
- 🚀 **No installation required** - everything runs on GitHub's servers

---

## 🚀 Step-by-Step Setup

### Step 1: Fork This Repository

1. **Click the "Fork" button** at the top-right corner of this page
2. Wait for GitHub to create your own copy of this repository
3. You now have your own version at `https://github.com/YOUR_USERNAME/REPO_NAME`

<div align="center">

![Fork Button Location](https://docs.github.com/assets/cb-40742/mw-1440/images/help/repository/fork-button.webp)

</div>

---

### Step 2: Enable GitHub Actions Permissions

1. Go to your forked repository
2. Click on **Settings** tab (top menu)
3. In the left sidebar, click **Actions** → **General**
4. Scroll down to **Workflow permissions**
5. Select **"Read and write permissions"**
6. Check **"Allow GitHub Actions to create and approve pull requests"** (optional)
7. Click **Save** button

<div align="center">
