# yt2drive

Download YouTube videos directly into Google Drive using Google Colab. No local installation required, runs directly in your browser.

---

## How It Works

```text
YouTube Link -> Colab Download (~1Gbps) -> Save to Google Drive
```

Your computer does not need to perform heavy processing; you can close the browser tab once execution begins.

---

## Usage Instructions

1. Upload `YouTube_to_Google_Drive.ipynb` to [colab.research.google.com](https://colab.research.google.com)
2. **Cell 1** — Install required libraries
3. **Cell 2** — Mount Google Drive (sign in with your Google account)
4. **Cell 3** — Provide URL and configuration settings
5. **Cell 4** — Run cell and wait for execution to complete

---

## Configuration (Cell 3)

```python
YOUTUBE_URL = 'https://youtube.com/watch?v=...'
DRIVE_FOLDER = 'YouTube Downloads'   # Destination folder in Google Drive
QUALITY = 'best'                     # options: best | 1080 | 720 | 480 | audio_only
DOWNLOAD_PLAYLIST = False            # True to download entire playlist
```

| Quality Option | Resolution / Output |
|---|---|
| `best` | Highest available quality |
| `1080` / `720` / `480` | Target video resolution |
| `audio_only` | Audio extraction (MP3) |

---

## Examples

```python
# HD 720p Video
QUALITY = '720'
DRIVE_FOLDER = 'Lectures/Python'

# Audio Extraction (MP3)
QUALITY = 'audio_only'
DRIVE_FOLDER = 'Music'

# Full Playlist Download
DOWNLOAD_PLAYLIST = True
DRIVE_FOLDER = 'Courses/Course Name'
```

### Batch Processing Multiple Videos

Use the **Bonus Cell** inside the notebook:

```python
URL_LIST = [
    'https://youtube.com/watch?v=VIDEO_1',
    'https://youtube.com/watch?v=VIDEO_2',
    'https://youtube.com/watch?v=VIDEO_3',
]
DRIVE_FOLDER_BATCH = 'YouTube Downloads/Batch'
QUALITY_BATCH = '720'
```

The script processes and downloads videos sequentially into the specified Google Drive folder.

---

## Pricing & Requirements

| Component | Cost / Limit |
|---|---|
| Google Colab | Free (~12h runtime per session) |
| Google Drive | Free up to 15 GB storage |

> Note: A 1-hour 1080p HD video typically requires 1–3 GB of storage.

---

## Frequently Asked Questions (FAQ)

**Download failed?**
Check if the video is age-restricted or geo-blocked in your region.

**File not appearing in Google Drive?**
Verify the `DRIVE_FOLDER` directory path in your configuration.

**Colab disconnects during long downloads?**
Open browser Developer Console (F12 -> Console) and run:
```javascript
setInterval(() => document.querySelector('colab-toolbar-button#connect').click(), 60000)
```

---

## Technical Stack

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) — High-performance YouTube downloader
- Google Colab & Google Drive — Cloud execution and storage environment

---

## License

MIT License — **yt2drive**
