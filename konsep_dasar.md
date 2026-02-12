# Konsep Dasar Clustering

**Clustering** adalah metode analisis data yang digunakan untuk mengelompokkan objek-objek data ke dalam grup atau *cluster* berdasarkan kemiripan atau kesamaan fitur. Tujuan utamanya adalah mengidentifikasi struktur atau pola tersembunyi dalam data **tanpa memerlukan label** yang telah ditentukan sebelumnya.

Clustering termasuk dalam teknik **unsupervised learning**, yaitu model tidak dilatih menggunakan data berlabel, melainkan hanya menggunakan fitur data untuk menemukan pola.

---

## Ilustrasi Sederhana Clustering

Bayangkan Anda seorang pustakawan yang baru menerima koleksi buku baru. Anda harus menyusun buku ke dalam rak tanpa mengetahui kategori sebelumnya.

Langkah yang dilakukan:

- Mengumpulkan semua buku
- Mengamati fitur utama (misalnya genre)
- Mengelompokkan buku berdasarkan kemiripan genre

Hasilnya:
- Buku fiksi berada di satu rak
- Buku non-fiksi di rak lain
- Buku ilmiah di rak berbeda

Proses ini mirip dengan **clustering**: mengelompokkan data berdasarkan kesamaan fitur tanpa label awal.

---

# Proses Clustering: Langkah Demi Langkah

Berikut tahapan umum dalam proses clustering:

1. Pengumpulan Data  
2. Pemilihan Fitur  
3. Pra-pemrosesan Data  
4. Pemilihan Metode Pengukuran Jarak  
5. Pemilihan Algoritma Clustering  
6. Penerapan Algoritma Clustering  
7. Evaluasi Hasil Clustering  
8. Interpretasi dan Tindakan  

---

## 1️⃣ Pengumpulan Data

Tahap awal adalah mengumpulkan data relevan yang akan dianalisis. Data dapat berupa:

- Numerik
- Kategorikal
- Teks

Contoh: segmentasi pelanggan menggunakan data usia, pendapatan, dan riwayat pembelian.

### Contoh Data Pelanggan

| ID | Usia | Pendapatan (Juta IDR) | Riwayat Pembelian |
|----|------|------------------------|-------------------|
| 1 | 25 | 5.0 | Elektronik |
| 2 | 30 | 8.0 | Pakaian |
| 3 | 22 | 4.5 | Elektronik |
| 4 | 35 | 0.0 | Pakaian |
| 5 | 29 | 6.0 | Elektronik |

Data harus valid dan cukup untuk menemukan pola yang bermakna.

---

## 2️⃣ Pemilihan Fitur

Fitur adalah atribut yang digunakan untuk proses pengelompokan. Pilih fitur yang:

- Relevan dengan tujuan analisis
- Mampu membedakan kelompok data

Contoh fitur terpilih: **usia** dan **pendapatan**.

### Contoh Fitur Terpilih

| ID | Usia | Pendapatan |
|----|------|------------|
| 1 | 25 | 5.0 |
| 2 | 30 | 8.0 |
| 3 | 22 | 4.5 |
| 4 | 35 | 0.0 |
| 5 | 29 | 6.0 |

Fitur yang tidak relevan dapat menurunkan kualitas clustering.

---

## 3️⃣ Pra-pemrosesan Data

Tahap pembersihan dan penyiapan data, meliputi:

- Menangani nilai hilang
- Menghapus duplikasi
- Normalisasi skala fitur

Normalisasi penting agar setiap fitur memiliki kontribusi setara.

### Contoh Data Setelah Normalisasi

| ID | Usia (Norm) | Pendapatan (Norm) |
|----|-------------|-------------------|
| 1 | 0.231 | 0.625 |
| 2 | 0.615 | 1.000 |
| 3 | 0.000 | 0.563 |
| 4 | 1.000 | 0.000 |
| 5 | 0.538 | 0.750 |

---

## 4️⃣ Pemilihan Metode Pengukuran Jarak

Digunakan untuk mengukur kemiripan antar data.

Metode umum:

- **Euclidean Distance** → data numerik
- **Cosine Similarity** → data teks/dokumen
- **Manhattan Distance**
- **Minkowski Distance**

### Contoh Jarak Euclidean (Ringkas)

| Pasangan | Jarak |
|-----------|--------|
| 1–2 | 0.537 |
| 1–3 | 0.239 |
| 1–4 | 0.722 |
| 1–5 | 0.322 |
| 4–5 | 0.809 |

Semakin kecil jarak → semakin mirip.

---

## 5️⃣ Pemilihan Algoritma Clustering

Beberapa algoritma populer:

### 🔹 K-Means
- Perlu jumlah cluster (K) di awal
- Cocok untuk cluster berbentuk relatif bulat

### 🔹 DBSCAN
- Tidak perlu jumlah cluster di awal
- Baik untuk bentuk cluster tidak beraturan
- Bisa mendeteksi noise

### 🔹 Hierarchical Clustering
- Membentuk struktur bertingkat (*dendrogram*)

Pemilihan tergantung jenis data dan tujuan analisis.

---

## 6️⃣ Penerapan Algoritma Clustering

Algoritma diterapkan ke data untuk membentuk cluster.

### Contoh Hasil K-Means

| ID | Usia | Pendapatan | Riwayat | Cluster |
|----|------|------------|----------|----------|
| 1 | 25 | 5.0 | Elektronik | 1 |
| 2 | 30 | 8.0 | Pakaian | 2 |
| 3 | 22 | 4.5 | Elektronik | 1 |
| 4 | 35 | 0.0 | Pakaian | 2 |
| 5 | 29 | 6.0 | Elektronik | 1 |

---

## 7️⃣ Evaluasi Hasil Clustering

Digunakan untuk menilai kualitas cluster.

Metrik umum:

- **Silhouette Score** → semakin mendekati 1 semakin baik
- **Davies–Bouldin Index** → semakin kecil semakin baik
- **Calinski–Harabasz Index**

### Contoh Silhouette Score

| ID | Score |
|----|--------|
| 1 | 0.68 |
| 2 | 0.77 |
| 3 | 0.71 |
| 4 | 0.72 |
| 5 | 0.65 |

---

## 8️⃣ Interpretasi dan Tindakan

Hasil clustering harus ditafsirkan untuk pengambilan keputusan.

### Contoh Interpretasi

- **Cluster 1**: usia lebih muda, pendapatan menengah, suka elektronik
- **Cluster 2**: usia lebih tua, pendapatan tinggi, suka pakaian

### Contoh Tindakan

- Promosi elektronik untuk Cluster 1
- Penawaran eksklusif pakaian untuk Cluster 2

---

# Kesimpulan

Clustering membantu menemukan pola tersembunyi dalam data tanpa label. Teknik ini bermanfaat untuk:

- Segmentasi pasar
- Deteksi anomali
- Pengelompokan dokumen
- Analisis perilaku

Dengan pemilihan fitur, algoritma, dan evaluasi yang tepat, clustering dapat mendukung pengambilan keputusan berbasis data secara lebih strategis.
