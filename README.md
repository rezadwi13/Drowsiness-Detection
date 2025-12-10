# Drowsiness Detection Web App

Aplikasi deteksi kantuk berbasis EAR (Eye Aspect Ratio) yang dijalankan dengan MediaPipe JS

---

## Deployment (Vercel)

Aplikasi sudah di-deploy di: [https://drowsiness-detection.vercel.app](https://drowsiness-detection.vercel.app)

---

## Cara Menjalankan Lokal (Flask + MediaPipe JS)

Deteksi dijalankan di browser menggunakan MediaPipe FaceMesh JS. Flask hanya menyajikan file HTML/JS/CSS.

### Prasyarat
- Windows, Python 3.9+

### Instalasi
1. Buat dan aktifkan virtual environment:
   ```powershell
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```
2. Instal Flask:
   ```powershell
   pip install Flask
   ```

### Menjalankan
```powershell
python app_flask.py
```
- Buka http://127.0.0.1:5000
- Klik "Start Camera" untuk izin kamera.
- Jika alarm tidak berbunyi pertama kali, klik halaman sekali (kebijakan autoplay audio di browser).

### Troubleshooting
- Izin kamera: pastikan browser mengizinkan akses kamera untuk `http://127.0.0.1:5000`.
- Audio tidak bunyi: klik halaman/tekan tombol agar audio context aktif.
- `favicon.ico` 404: tidak berpengaruh pada fungsi, bisa diabaikan.

---

## Struktur Folder
```
.
├─ app_flask.py          # Server Flask untuk menyajikan halaman
├─ templates/
│  └─ index.html         # Halaman utama (Flask mode)
├─ static/
│  └─ js/app.js          # Logika deteksi EAR di browser
└─ .venv/                # Virtual environment (opsional)
```

---

## Tambahan
- Disarankan menggunakan `requirements.txt` (sudah disertakan):
  - `Flask`
- Versi Python disarankan 3.9–3.11 agar kompatibel dengan pustaka terkait.

---

## Lisensi
Gunakan untuk keperluan pembelajaran/riset. Sesuaikan lisensi sesuai kebutuhan proyek Anda.
