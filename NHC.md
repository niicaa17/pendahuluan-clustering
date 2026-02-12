# Non-hierarchical Clustering (NHC)

**Non-hierarchical clustering (NHC)** adalah metode pengelompokan data yang tidak membentuk struktur hierarkis atau dendrogram seperti pada hierarchical clustering.  

Sebaliknya, NHC berfokus pada pembentukan **cluster terpisah** berdasarkan kriteria tertentu tanpa memperhitungkan hubungan antar cluster dalam bentuk hierarki.

Metode ini sering digunakan ketika:

- Jumlah cluster sudah ditentukan sebelumnya
- Dibutuhkan pendekatan yang lebih sederhana dan cepat
- Dataset berukuran besar

---

# Metode Non-hierarchical Clustering

Non-hierarchical clustering mencakup beberapa algoritma populer yang sering digunakan dalam praktik.

---

## 🔹 K-Means Clustering

**K-Means** adalah metode clustering yang membagi data ke dalam **k cluster** berdasarkan jarak terdekat ke **centroid** (titik pusat cluster), yang dihitung sebagai rata-rata anggota cluster.

Metode ini populer karena:

- Sederhana
- Cepat
- Efisien untuk data besar
- Cocok untuk cluster berbentuk relatif bulat

### Cara Kerja Singkat

1. Tentukan jumlah cluster (k)
2. Inisialisasi centroid secara acak
3. Assign tiap data ke centroid terdekat (biasanya Euclidean distance)
4. Hitung ulang centroid sebagai rata-rata cluster
5. Ulangi sampai centroid stabil (konvergen)

### Kelebihan

- ✅ Mudah dipahami dan diimplementasikan  
- ✅ Komputasi cepat  
- ✅ Cocok untuk dataset besar  

### Kekurangan

- ❌ Harus menentukan nilai k di awal  
- ❌ Sensitif terhadap outliers  
- ❌ Kurang cocok untuk bentuk cluster tidak beraturan  

---

## 🔹 K-Medoids Clustering

**K-Medoids** adalah varian K-Means yang menggunakan **titik data nyata** sebagai pusat cluster (medoid), bukan rata-rata.

Karena pusatnya adalah data asli, metode ini lebih tahan terhadap noise dan outliers.

Cocok untuk:
- Data medis
- Data sensor
- Data dengan banyak outlier

### Cara Kerja Singkat

1. Tentukan jumlah cluster (k)
2. Pilih medoid awal dari data
3. Assign tiap data ke medoid terdekat
4. Uji kandidat medoid baru dalam cluster
5. Pilih medoid yang meminimalkan total jarak
6. Ulangi sampai stabil

### Kelebihan

- ✅ Lebih robust terhadap outliers  
- ✅ Pusat cluster lebih representatif  

### Kekurangan

- ❌ Lebih lambat dari K-Means  
- ❌ Tetap perlu menentukan k di awal  

---

## 🔹 DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

**DBSCAN** adalah metode clustering berbasis **kepadatan (density)**. Algoritma ini membentuk cluster dari area yang padat dan menandai titik jarang sebagai **noise**.

Tidak perlu menentukan jumlah cluster di awal.

Cocok untuk:
- Bentuk cluster tidak beraturan
- Data spasial/geografis
- Deteksi anomali

### Parameter Utama

- **ε (epsilon)** → radius jarak tetangga
- **MinPts** → jumlah minimum titik untuk membentuk area padat

### Cara Kerja Singkat

1. Tentukan ε dan MinPts
2. Temukan titik dengan tetangga cukup → core point
3. Bentuk cluster dari core point
4. Perluas cluster ke tetangga padat
5. Titik yang tidak memenuhi → noise

### Kelebihan

- ✅ Tidak perlu jumlah cluster  
- ✅ Menangani noise  
- ✅ Menemukan bentuk arbitrer  

### Kekurangan

- ❌ Sensitif pemilihan parameter  
- ❌ Kurang efisien pada data sangat besar  
- ❌ Sulit untuk kepadatan yang bervariasi  

---

## 🔹 Mean Shift Clustering

**Mean Shift** adalah metode berbasis kepadatan yang mencari **pusat kepadatan (mode)** dengan menggeser titik ke arah rata-rata lokal secara berulang.

Tidak perlu menentukan jumlah cluster di awal.

Cocok untuk:
- Analisis citra
- Data spasial
- Pola kompleks

### Cara Kerja Singkat

1. Tentukan ukuran jendela (bandwidth/kernel)
2. Untuk tiap titik → hitung rata-rata tetangga
3. Geser titik ke rata-rata tersebut
4. Ulangi sampai konvergen
5. Titik yang bertemu → satu cluster

### Kelebihan

- ✅ Tidak perlu jumlah cluster  
- ✅ Menangani bentuk cluster kompleks  

### Kekurangan

- ❌ Sensitif ukuran bandwidth  
- ❌ Komputasi berat untuk data besar  

---

# Ringkasan Perbandingan Singkat

| Metode | Perlu k | Tahan Outlier | Bentuk Bebas | Deteksi Noise |
|---------|----------|---------------|---------------|---------------|
| K-Means | Ya | Tidak | Kurang | Tidak |
| K-Medoids | Ya | Lebih tahan | Cukup | Tidak |
| DBSCAN | Tidak | Ya | Ya | Ya |
| Mean Shift | Tidak | Ya | Ya | Sebagian |

---

# Kesimpulan

Non-hierarchical clustering berfokus pada pembentukan cluster langsung tanpa struktur hierarki. Metode ini:

- Lebih cepat untuk data besar
- Lebih praktis untuk implementasi
- Fleksibel sesuai karakteristik data

Pemilihan metode terbaik bergantung pada:

- Bentuk cluster
- Ukuran data
- Keberadaan noise
- Apakah jumlah cluster diketahui

Pada materi berikutnya, pembahasan biasanya difokuskan lebih dalam pada **K-Means** dan **DBSCAN** sebagai dua metode NHC yang paling sering digunakan.
