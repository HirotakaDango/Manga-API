# PHPMusicPost &ndash; Manga Studio

<img width="720" height="400" alt="screenshot" src="https://github.com/user-attachments/assets/2c10e9a1-292b-4819-ae76-61e3e79c69ae" />

A lightweight, standalone frontend client and cinema manga reader designed to consume the artwork API from [PHP-Music](https://github.com/HirotakaDango/PHP-Music).

---

## 📖 Overview

This is a single-file portable web client (`index.html`) that connects to a **PHP-Music** backend instance (`index.php?access=artwork`). It isolates and curates all **Manga** submissions into a dedicated reading hub without loading unrelated illustrations, audio, or video posts.

---

## ✨ Features

- **Pure Vanilla Web Stack**: Single-file app built with HTML5, CSS3, and Vanilla JS. Zero npm builds or heavy frameworks.
- **Dual Reading Modes**:
  - **Single Page**: Classical reader with left/center/right touch zones and arrow key navigation.
  - **Webtoon Mode**: Continuous vertical scroll stream with auto-updating page indicators.
- **Persistent Cinema HUD**: Tap center to hide UI toolbars; keeps toolbars hidden across page turns until tapped again.
- **Strict Manga Scoping**: Catalogs, search results, and directories (Tags, Characters, Parodies, and Authors) strictly filter out non-manga artwork.
- **Smart URL Normalization**: Point the client directly to your root domain (e.g., `https://phpmusic.rf.gd`) without manually typing `/index.php?access=artwork`.
- **Dynamic API Icons**: Automatically pulls the site icon via `action=get_app_icon`.
- **Red-Dark UI**: High-contrast dark theme optimized for OLED screens and reading comfort.
- **Content Filters**: Built-in R-18 toggle and interactive Safe-Blur overlays.

---

## 🚀 Quick Start

1. Download or place `index.html` on any static host (GitHub Pages, Apache, Nginx, or open directly in your browser).
2. Open the sidebar and click **Studio Settings** (`⚙`).
3. Enter your PHP-Music base URL (e.g., `https://your-site.com`).
4. Click **Save & Connect**.

---

## 🔌 Consumed API Endpoints

The client communicates with the PHP-Music artwork router (`index.php?access=artwork&action=...`):

| Action | Purpose |
| :--- | :--- |
| `manga_series_list` | Fetches grouped manga series with chapter counts, view metrics, and sorting. |
| `manga_series_get` | Retrieves series details, metadata, and full chapter tracklist. |
| `manga_chapter_get` | Loads chapter page images and adjacent chapter sibling data. |
| `artworks_list` | Queries raw manga artworks (`feed=manga`) to extract tags, parodies, and characters. |
| `thumb` / `raw` | Streams thumbnail previews and full-resolution manga page assets. |
| `get_app_icon` | Dynamically streams the application SVG icon for favicon and branding. |
