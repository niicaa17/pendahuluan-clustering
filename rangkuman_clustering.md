# Rangkuman Unsupervised Learning — Clustering

## 📌 Konsep Dasar Clustering

Clustering adalah teknik **unsupervised learning** untuk mengelompokkan data ke dalam beberapa grup berdasarkan kemiripan fitur tanpa memerlukan label. Tujuannya adalah menemukan pola atau struktur tersembunyi dalam data.

Clustering banyak digunakan untuk:
- Segmentasi pelanggan
- Pengelompokan dokumen
- Analisis citra
- Deteksi anomali
- Analisis perilaku pengguna

---

# ⚙️ Tahapan Proses Clustering

1️⃣ **Pengumpulan Data**  
Mengumpulkan data relevan untuk dianalisis, misalnya data pelanggan (usia, pendapatan, riwayat pembelian).

2️⃣ **Pemilihan Fitur**  
Memilih fitur yang paling relevan dengan tujuan analisis.

3️⃣ **Pra-pemrosesan Data**  
Membersihkan data, menghapus duplikasi, menangani missing value, dan melakukan normalisasi skala.

4️⃣ **Pemilihan Metode Jarak**  
Menentukan ukuran kemiripan, misalnya:
- Euclidean distance
- Manhattan distance
- Cosine similarity

5️⃣ **Pemilihan Algoritma Clustering**  
Memilih metode seperti K-Means, DBSCAN, atau Hierarchical Clustering.

6️⃣ **Penerapan Algoritma**  
Menjalankan algoritma untuk membentuk cluster.

7️⃣ **Evaluasi Hasil**  
Menilai kualitas cluster dengan metrik seperti silhouette score atau WCSS.

8️⃣ **Interpretasi & Tindakan**  
Menganalisis hasil dan mengambil keputusan berbasis cluster.

---

# 🌳 Hierarchical Clustering (HC)

Hierarchical Clustering membentuk **struktur hierarki cluster** yang digambarkan dalam **dendrogram**.

## Pendekatan HC

### 🔼 Agglomerative (Bottom-Up)
- Setiap data mulai sebagai cluster tunggal
- Cluster digabung bertahap
- Berakhir menjadi satu cluster besar

### 🔽 Divisive (Top-Down)
- Mulai dari satu cluster besar
- Dipecah menjadi cluster lebih kecil

## Ciri HC
- Tidak perlu menentukan jumlah cluster di awal
- Bisa dipotong pada level tertentu di dendrogram
- Cocok untuk dataset kecil–menengah

---

# 🧩 Non-Hierarchical Clustering (NHC)

Non-hierarchical clustering membentuk cluster **tanpa struktur pohon**. Fokus pada pembagian langsung data menjadi kelompok terpisah berdasarkan jarak atau kepadatan.

---

# 🎯 Metode Non-Hierarchical Clustering

## 🔵 K-Means Clustering

Mengelompokkan data ke dalam **k cluster** berdasarkan jarak ke centroid.

### Cara Kerja
- Tentukan jumlah cluster (k)
- Inisialisasi centroid
- Assign data ke centroid terdekat
- Update centroid (rata-rata)
- Iterasi sampai stabil

### Kelebihan
- Sederhana
- Cepat
- Scalable untuk data besar

### Kekurangan
- Harus tentukan k di awal
- Sensitif terhadap outlier
- Cocok hanya untuk data numerik
- Asumsi cluster cenderung bulat

---

## 🟢 K-Medoids Clustering

Mirip K-Means, tetapi pusat cluster adalah **data nyata (medoid)**, bukan rata-rata.

### Kelebihan
- Lebih tahan terhadap outlier
- Pusat cluster lebih representatif

### Kekurangan
- Lebih lambat dari K-Means
- Tetap perlu jumlah cluster di awal

---

## 🟣 DBSCAN

Clustering berbasis **kepadatan** yang dapat menemukan bentuk cluster tidak beraturan dan mendeteksi noise.

### Parameter
- ε (epsilon): radius tetangga
- MinPts: minimum titik untuk membentuk cluster

### Kelebihan
- Tidak perlu jumlah cluster
- Menangani noise
- Bentuk cluster bebas

### Kekurangan
- Sensitif parameter
- Kurang efisien untuk data sangat besar
- Sulit untuk kepadatan tidak merata

---

## 🟠 Mean Shift

Metode berbasis kepadatan yang menggeser titik ke pusat kepadatan lokal.

### Cara Kerja
- Tentukan bandwidth (kernel window)
- Geser titik ke rata-rata tetangga
- Gabungkan titik konvergen

### Kelebihan
- Tidak perlu jumlah cluster
- Menangani bentuk kompleks

### Kekurangan
- Komputasi berat
- Sensitif bandwidth
- Lambat untuk dataset besar

---

# 📏 Evaluasi Clustering (Ringkas)

Beberapa metrik penting:

- **WCSS** → kepadatan dalam cluster
- **Elbow Method** → menentukan k optimal
- **Silhouette Score** → kualitas pemisahan cluster
- **Visualisasi** → validasi pola

---

# ✅ Inti Utama

Clustering membantu menemukan struktur data tanpa label dengan:

- Proses preprocessing yang baik
- Pemilihan algoritma sesuai karakter data
- Evaluasi menggunakan beberapa metrik
- Interpretasi hasil untuk pengambilan keputusan
