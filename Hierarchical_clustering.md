# Hierarchical Clustering (HC)

Metode clustering secara umum dibagi menjadi dua kategori utama:

- **Hierarchical Clustering**
- **Non-Hierarchical Clustering**

Pada bagian ini kita membahas **Hierarchical Clustering (HC)**.

---

## Pengertian Hierarchical Clustering

**Hierarchical clustering** adalah teknik clustering yang mengelompokkan data dalam bentuk **hierarki bertingkat** berdasarkan kemiripan atau jarak antar objek.

Metode ini membangun struktur bertahap yang menunjukkan bagaimana cluster:

- digabung → dari kecil ke besar  
- atau dipecah → dari besar ke kecil  

Hasilnya biasanya divisualisasikan dalam bentuk **dendrogram** (diagram pohon).

Hierarchical clustering memiliki dua pendekatan utama:

- **Agglomerative (bottom-up)**
- **Divisive (top-down)**

---

# Pendekatan Hierarchical Clustering

## 🔹 Agglomerative (Bottom-Up)

Agglomerative hierarchical clustering dimulai dengan pendekatan **bottom-up**:

- Setiap objek dianggap sebagai **1 cluster** di awal
- Jika ada `n` objek → ada `n` cluster awal
- Kemudian cluster digabung secara bertahap

### Prosesnya:

1. Hitung jarak antar semua pasangan cluster
2. Pilih dua cluster dengan jarak terdekat
3. Gabungkan menjadi cluster baru
4. Ulangi sampai semua objek menjadi satu cluster besar

### Dendrogram

- Sumbu vertikal → jarak/kemiripan saat penggabungan
- Sumbu horizontal → cluster yang digabung

---

## 🔹 Divisive (Top-Down)

Divisive hierarchical clustering menggunakan pendekatan **top-down**:

- Mulai dari **satu cluster besar** berisi semua objek
- Cluster besar dipecah menjadi cluster lebih kecil
- Proses berlanjut sampai tiap objek menjadi cluster sendiri

### Prosesnya:

1. Mulai dari satu cluster global
2. Bagi menjadi dua sub-cluster
3. Pilih cluster yang masih heterogen
4. Pecah lagi
5. Ulangi sampai tingkat detail yang diinginkan

Hasilnya juga divisualisasikan dengan **dendrogram**.

---

## Perbedaan Inti Pendekatan

### Agglomerative
- Mulai dari: `a b c d e`
- Digabung bertahap → `abcde`

### Divisive
- Mulai dari: `abcde`
- Dipecah bertahap → `a b c d e`

---

# Metode Linkage dalam Hierarchical Clustering

**Linkage** menentukan bagaimana jarak antar cluster dihitung saat proses penggabungan/pemisahan.

---

## 🔹 Single Linkage (Nearest Neighbor)

- Jarak cluster = **jarak terdekat** antar anggota dua cluster
- Menggunakan pasangan titik paling dekat

**Kelebihan:**
- Baik untuk bentuk cluster memanjang

**Kelemahan:**
- Menyebabkan *chaining effect* (efek rantai)
- Cluster bisa memanjang dan tidak kompak

---

## 🔹 Complete Linkage (Farthest Neighbor)

- Jarak cluster = **jarak terjauh** antar anggota dua cluster

**Kelebihan:**
- Cluster lebih kompak
- Lebih terpisah jelas

**Kelemahan:**
- Sensitif terhadap outlier

---

## 🔹 Average Linkage

- Jarak cluster = **rata-rata jarak** seluruh pasangan titik antar cluster

**Karakteristik:**
- Lebih seimbang
- Mengurangi efek ekstrem single & complete linkage
- Sering dipakai dalam praktik

---

## 🔹 Centroid Linkage

- Jarak cluster = jarak antar **centroid (titik pusat)** cluster

### Langkah:
- Hitung centroid tiap cluster
- Ukur jarak antar centroid
- Jika digabung → hitung centroid baru

**Kelebihan:**
- Berdasarkan posisi pusat
- Cluster relatif seimbang

---

## 🔹 Ward’s Linkage

- Menggabungkan cluster yang menghasilkan **kenaikan variasi terkecil**
- Meminimalkan *within-cluster variance*

**Karakteristik:**
- Cluster sangat kompak
- Homogen
- Sering memberi hasil rapi

---

# Metode Pengukuran Jarak (Distance)

Distance metric sangat penting dalam hierarchical clustering karena menentukan kemiripan data.

---

## 📏 Euclidean Distance

Mengukur jarak garis lurus antar dua titik.

**Karakteristik:**
- Paling umum digunakan
- Cocok untuk data numerik kontinu
- Sensitif terhadap skala → perlu normalisasi

**Konsep:**
> Akar dari jumlah kuadrat selisih tiap dimensi

---

## 📏 Manhattan Distance

Disebut juga **city block distance**.

**Karakteristik:**
- Menjumlahkan selisih absolut tiap dimensi
- Cocok untuk data berbasis grid
- Lebih tahan terhadap outlier dibanding Euclidean

**Konsep:**
> Jumlah |selisih| tiap dimensi

---

## 📏 Minkowski Distance

Generalisasi dari Euclidean dan Manhattan.

Menggunakan parameter **p**:

- p = 1 → Manhattan
- p = 2 → Euclidean
- p > 2 → bentuk jarak lain

Memberi fleksibilitas dalam pengukuran jarak.

---

# Kelebihan Hierarchical Clustering

✅ Tidak perlu menentukan jumlah cluster di awal  
✅ Menghasilkan struktur hierarki  
✅ Visualisasi jelas dengan dendrogram  
✅ Fleksibel untuk berbagai bentuk data  

---

# Kekurangan Hierarchical Clustering

❌ Kurang skalabel untuk data sangat besar  
❌ Sensitif terhadap noise dan outlier  
❌ Sulit menentukan jumlah cluster optimal  
❌ Biaya komputasi tinggi  

---

# Kesimpulan

Hierarchical clustering sangat efektif untuk:

- Memahami struktur data secara bertingkat
- Analisis eksploratif
- Visualisasi hubungan antar data

Dengan memahami:
- pendekatan (agglomerative vs divisive),
- metode linkage,
- dan distance metric,

Anda dapat memilih konfigurasi yang paling sesuai untuk menghasilkan cluster yang relevan dan mudah diinterpretasikan.
