# 🎬 yt2drive

Tải video YouTube lưu vào Google Drive qua Google Colab. Không cần cài đặt, chạy trên trình duyệt.

---

## ⚡ Cách hoạt động

```
Link YouTube → Colab tải (~1Gbps) → Lưu vào Drive
```

Máy tính bạn không cần làm gì, có thể tắt màn hình.

---

## 🚀 Sử dụng

1. Upload `YouTube_to_Google_Drive.ipynb` lên [colab.research.google.com](https://colab.research.google.com)
2. **Cell 1** — Cài thư viện
3. **Cell 2** — Kết nối Google Drive (đăng nhập Google)
4. **Cell 3** — Điền URL + cấu hình
5. **Cell 4** — Chạy và chờ

---

## ⚙️ Cấu hình (Cell 3)

```python
YOUTUBE_URL = 'https://youtube.com/watch?v=...'
DRIVE_FOLDER = 'YouTube Downloads'   # Thư mục lưu trong Drive
QUALITY = 'best'   # best | 1080 | 720 | 480 | audio_only
DOWNLOAD_PLAYLIST = False            # True = tải cả playlist
```

| Quality | Kết quả |
|---|---|
| `best` | Chất lượng cao nhất |
| `1080` / `720` / `480` | Theo độ phân giải |
| `audio_only` | MP3 |

---

## 💡 Ví dụ

```python
# Bài giảng 720p
QUALITY = '720'
DRIVE_FOLDER = 'Bài giảng/Python'

# Tải nhạc MP3
QUALITY = 'audio_only'
DRIVE_FOLDER = 'Music'

# Cả playlist
DOWNLOAD_PLAYLIST = True
DRIVE_FOLDER = 'Khoá học/Tên khoá'
```

**Nhiều video cùng lúc** → Dùng **Cell Bonus** trong notebook:

```python
URL_LIST = [
    'https://youtube.com/watch?v=VIDEO_1',
    'https://youtube.com/watch?v=VIDEO_2',
    'https://youtube.com/watch?v=VIDEO_3',
]
DRIVE_FOLDER_BATCH = 'YouTube Downloads/Batch'
QUALITY_BATCH = '720'
```

Tool sẽ tải tuần tự từng video và lưu vào cùng một thư mục Drive.

---

## 💰 Chi phí

| | Giá |
|---|---|
| Google Colab | Miễn phí (~12h/phiên) |
| Google Drive | Miễn phí đến 15 GB |

> 1 video HD ~1 giờ ≈ 1–3 GB.

---

## ❓ FAQ

**Lỗi không tải được?** → Video bị giới hạn vùng. Thử video khác.

**Không thấy file trong Drive?** → Kiểm tra lại tên `DRIVE_FOLDER`.

**Colab tự ngắt khi tải dài?** → F12 → Console → dán:
```javascript
setInterval(() => document.querySelector('colab-toolbar-button#connect').click(), 60000)
```

---

## 📦 Công nghệ

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) — tải video
- Google Colab + Drive — chạy và lưu trữ

---

## 📄 License

MIT — **yt2drive**
