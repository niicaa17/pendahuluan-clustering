# DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

DBSCAN adalah algoritma clustering berbasis **kepadatan data** yang mengelompokkan titik-titik berdasarkan seberapa rapat mereka berada di suatu area. Berbeda dengan K-Means, DBSCAN tidak memerlukan jumlah cluster di awal dan mampu mendeteksi data noise (outlier).

---

## 🎯 Konsep Inti DBSCAN

DBSCAN menggunakan dua parameter utama:

### 1. Epsilon (ε)
- Jarak maksimum antar titik agar dianggap bertetangga
- Dapat dibayangkan sebagai radius lingkaran di sekitar titik

### 2. MinPts
- Jumlah minimum tetangga dalam radius ε agar titik dianggap sebagai pusat cluster (core point)

---

## 🧩 Jenis Titik pada DBSCAN

### 🔵 Core Point
- Memiliki jumlah tetangga ≥ MinPts dalam radius ε
- Menjadi pusat pembentukan cluster

### 🟡 Border Point
- Tetangga dari core point
- Tidak memenuhi MinPts
- Tetap masuk ke cluster

### 🔴 Noise Point (Outlier)
- Tidak memiliki cukup tetangga
- Tidak terhubung ke core point
- Tidak masuk cluster mana pun

---

## ⚙️ Langkah Kerja DBSCAN

### Langkah 1 — Inisialisasi Parameter
Tentukan:
- Nilai ε (epsilon)
- Nilai MinPts

---

### Langkah 2 — Pilih Titik Awal
- Pilih satu titik yang belum diproses
- Hitung jumlah tetangga dalam radius ε

---

### Langkah 3 — Identifikasi Core Point
- Jika tetangga ≥ MinPts → titik adalah **core point**
- Bentuk cluster baru
- Masukkan semua tetangganya

Jika tidak:
- Tandai sebagai noise sementara

---

### Langkah 4 — Perluas Cluster
- Periksa tetangga dari core point
- Jika tetangga juga core point → perluas cluster
- Tambahkan semua titik yang density-connected

---

### Langkah 5 — Iterasi
- Ulangi proses ke titik lain yang belum diproses
- Berhenti saat semua titik sudah diklasifikasikan sebagai cluster atau noise

---

## 📊 Contoh Hasil DBSCAN

Hasil clustering DBSCAN biasanya menghasilkan:

- Cluster 1 → kelompok titik rapat area tertentu
- Cluster 2 → kelompok titik rapat area lain
- Noise → titik terpencil di luar kepadatan cluster

---

## ⭐ Kelebihan DBSCAN

- Tidak perlu menentukan jumlah cluster
- Mampu mendeteksi noise secara otomatis
- Bisa menemukan bentuk cluster tidak beraturan
- Lebih tahan terhadap outlier
- Cocok untuk data spasial dan geolokasi

---

## ⚠️ Kekurangan DBSCAN

- Sensitif terhadap pemilihan ε
- Sulit jika kepadatan cluster berbeda-beda
- Kurang optimal untuk data berdimensi tinggi
- Pemilihan parameter perlu percobaan

---

## 🔍 Perbandingan Singkat: K-Means vs DBSCAN

| Aspek | K-Means | DBSCAN |
|--------|----------|-----------|
| Jumlah cluster ditentukan di awal | Ya | Tidak |
| Bentuk cluster | Cenderung bulat | Bebas |
| Deteksi noise | Tidak | Ya |
| Sensitif outlier | Tinggi | Rendah |
| Dasar metode | Jarak ke centroid | Kepadatan |

---
