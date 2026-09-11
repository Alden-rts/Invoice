# 🤖 Bot Rekap Keuangan & Invoice Otomatis via Telegram & AI (Groq)

Sistem otomatisasi pencatatan transaksi keuangan bisnis menggunakan **Bot Telegram**, **Groq API (Vision & Audio)**, dan **Google Sheets API**. Cukup kirimkan foto struk belanja atau pesan suara (*voice note*), AI akan membaca nominal, nama toko, serta tanggal transaksi lalu mencatatnya secara instan ke Google Sheets.

---

## 📸 Fitur Utama

- **Foto Struk to Sheet:** Ekstraksi data otomatis dari foto struk belanja / invoice.
- **Voice Note to Sheet:** Transkrip dan ekstraksi nominal belanja via pesan suara.
- **Real-Time Integration:** Data transaksi langsung masuk ke baris baru di Google Sheets.
- **Gratis & Cepat:** Memanfaatkan Groq API (*LLm inference engine* super cepat) dan pyTelegramBotAPI.

---

## 🛠️ Arsitektur & Teknologi

| Komponen | Deskripsi |
| :--- | :--- |
| **Python 3.10+** | Bahasa pemrograman utama |
| **pyTelegramBotAPI** | Handling interface Bot Telegram |
| **Groq API** | Model AI pemroses teks, audio, dan gambar |
| **gspread & OAuth2** | Integrasi Google Sheets API |

---

## 🚀 Quick Start / Cara Menjalankan

### 1. Clone Repository
```bash
git clone [https://github.com/Alden-rts/bot-rekap-keuangan.git](https://github.com/Alden-rts/bot-rekap-keuangan.git)
cd bot-rekap-keuangan
```
### 2. Install Dependencies
```bash
pip install pyTelegramBotAPI groq gspread oauth2client python-dotenv
```

### 3. Setup Google Sheets API & Kredensial
1. Buka Google Cloud Console dan buat project baru.
2. Buka menu APIs & Services > Library, cari dan aktifkan:
- Google Sheets API
- Google Drive API
3. Masuk ke APIs & Services > Credentials > Klik Create Credentials > Pilih Service Account.
4. Isi nama Service Account, lalu klik Create and Continue sampai selesai.
5. klik Service Account yang baru dibuat > Buka tab Keys > Klik Add Key > Create new key > Pilih format JSON.
6. File JSON akan otomatis terunduh. Rename file tersebut menjadi credentials.json dan simpan di folder utama project ini.
7. Penting: Buka file credentials.json, salin email yang ada di baris "client_email". Buka Google Sheets target kamu, klik tombol Share/Bagikan, lalu paste email tersebut dan beri akses sebagai Editor.

### 4. Konfigurasi Environment (.env)
Buat file .env di direktori utama project dan isi kredensial berikut:
```bash
TELEGRAM_BOT_TOKEN="YOUR_TELEGRAM_BOT_TOKEN"
GROQ_API_KEY="YOUR_GROQ_API_KEY"
GOOGLE_SHEETS_ID="YOUR_GOOGLE_SHEETS_ID"
```
📌 Catatan
• Jangan lupa sertakan file Service Account Google (credentials.json) di folder yang sama untuk akses ke Google Sheets API.
• GOOGLE_SHEETS_ID dapat diambil dari URL Google Sheets kamu:
https://docs.google.com/spreadsheets/d/[ID_SPREADSHEET_KAMU]/edit

### 5. Jalankan Bot
```bash
python main.py
```

### 6. 📝 Lisensi & Kontribusi
Proyek ini bersifat open-source. Silakan fork, pelajari, atau kembangkan sesuai kebutuhan bisnis kamu!
