# Drowsiness Detection Web App

Aplikasi deteksi kantuk berbasis EAR (Eye Aspect Ratio) yang dijalankan dengan MediaPipe JS
<img width="1850" height="797" alt="image" src="https://github.com/user-attachments/assets/510b4e3f-250a-440d-a021-87fcd056c471" />

---

## Deployment (Vercel)

Aplikasi sudah di-deploy di: [https://drowsiness-detection-ecru.vercel.app](https://drowsiness-detection-ecru.vercel.app)

---

## Cara Menjalankan Lokal (Flask + MediaPipe JS)

Deteksi dijalankan di browser menggunakan MediaPipe FaceMesh JS. Flask hanya menyajikan file HTML/JS/CSS.

## Menjalankan Lokal (tanpa Flask)

Jika hanya ingin serve statis:

```powershell
python -m http.server 8000
```

Buka http://localhost:8000 lalu akses `index.html` di root.

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

### Troubleshooting (Produksi / Vercel)
- Aset 404 di `/static/...`: pastikan project menggunakan preset "Other" (static) dan domain mengarah ke project yang benar.
- Jika perubahan tidak terlihat: klik Redeploy (Clear build cache) atau Promote to Production untuk commit terbaru.
- Library MediaPipe dari CDN berubah versi: pertimbangkan pin versi stabil untuk konsistensi.

---

## Struktur Folder
```
.
├─ index.html               # Halaman utama (static deploy)
├─ static/
│  ├─ css/styles.css        # Style
│  └─ js/app.js             # Logika deteksi EAR di browser
├─ templates/
│  └─ index.html            # Hanya untuk mode Flask (opsional)
├─ app_flask.py             # Server Flask opsional untuk lokal
└─ .venv/                   # Virtual environment (opsional)
```

---

## Tambahan
- Disarankan menggunakan `requirements.txt` (sudah disertakan):
  - `Flask`
- Versi Python disarankan 3.9–3.11 agar kompatibel dengan pustaka terkait.

Pin versi CDN MediaPipe (opsional untuk kestabilan):
- `@mediapipe/face_mesh@0.4.1633559619/face_mesh.js`
- `@mediapipe/camera_utils@0.1.1640016670/camera_utils.js`
- `@mediapipe/drawing_utils@0.4.1640997471/drawing_utils.js`

---

## Lisensi
Gunakan untuk keperluan pembelajaran/riset. Sesuaikan lisensi sesuai kebutuhan proyek Anda.
