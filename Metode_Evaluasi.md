# Metode Evaluasi: Elbow Method

**Metode Elbow** adalah teknik evaluasi yang digunakan untuk menentukan jumlah cluster optimal dalam analisis clustering, khususnya pada algoritma **K-Means**.

---

## 📌 Definisi dan Prinsip Dasar

Metode Elbow menentukan jumlah cluster (**k**) yang ideal dengan menganalisis hubungan antara:

- Jumlah cluster (k)
- Total kesalahan kuadrat dalam cluster (**SSE – Sum of Squared Errors**)

**SSE** mengukur seberapa dekat titik data dengan centroid clusternya.  
Semakin kecil nilai SSE → semakin baik kualitas pengelompokan.

---

## 🎉 Analogi Sederhana

Bayangkan Anda mengatur pesta dengan **20 tamu** dan harus menentukan jumlah meja:

- 1 meja → terlalu padat
- 2 meja → lebih baik
- 3–4 meja → semakin nyaman
- 5 meja → peningkatan kenyamanan kecil

Pada titik tertentu, menambah meja tidak memberi manfaat besar.  
Titik itulah disebut **titik elbow (siku)** → jumlah meja optimal.

Dalam clustering:
- Meja = cluster
- Kerumunan = SSE
- Titik elbow = jumlah cluster terbaik

---

## 🎯 Tujuan Metode Elbow

Metode elbow membantu:

- Menentukan jumlah cluster optimal
- Menghindari terlalu banyak cluster (overfitting)
- Menjaga keseimbangan antara kompleksitas dan kualitas model
- Mengungkap struktur data secara lebih akurat

---

## ⚙️ Langkah-Langkah Metode Elbow

### 1️⃣ Tentukan Rentang k
Pilih nilai k yang akan diuji, misalnya:

