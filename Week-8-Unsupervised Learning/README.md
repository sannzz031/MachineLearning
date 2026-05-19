# Laporan Praktikum Unsupervised Learning - K-Means Clustering (Week 8)

Repositori ini berisi implementasi lengkap tugas praktikum *Unsupervised Learning* dengan fokus utama pada pengelompokan data menggunakan algoritma **K-Means Clustering**. Analisis dilakukan pada dataset antropometri sederhana untuk melihat pola pengelompokan fitur fisik tanpa menggunakan label target (*unsupervised*).

---

## 📌 Biodata Mahasiswa
* **Nama**: Josan Mauritz Sharon Nunuhitu  
* **NIM**: 4222301060  
* **Kelas**: RE-B Pagi (6)  
* **Instansi**: Politeknik Negeri Batam  
* **Dosen Pengampu**: Rifky Afriza  

---

## 📂 Ringkasan Dataset
Proyek ini menggunakan dataset lokal bernama `berat_tinggi.csv`. 
* **Fitur Utama (X)**: `berat` (Berat Badan - kg) dan `tinggi` (Tinggi Badan - cm).
* **Target Pembanding (y)**: Kolom `deskripsi` yang bertindak sebagai label asli dari anotator manusia untuk mengevaluasi kualitas hasil clustering.

---

## 🛠️ Alur Pipa Data (Data Pipeline)

Proyek dikerjakan secara sistematis melalui tahapan berikut di dalam notebook:

1. **Eksplorasi Data Awal (EDA)**:
   * Visualisasi sebaran data mentah dengan `sns.scatterplot`.
   * Analisis statistika deskriptif (`df.describe()`).
   * Deteksi pencilan (*outliers*) menggunakan Box Plot dan Histogram untuk masing-masing kolom fitur.
2. **Data Cleaning**:
   * Menghilangkan data duplikat menggunakan `df.drop_duplicates()` guna menjaga kebersihan data sebelum proses komputasi jarak jarak (*distance-based*).
3. **Feature Scaling (Standardization)**:
   * Menggunakan `StandardScaler` dari scikit-learn untuk mentransformasi nilai asli menjadi bentuk *z-score* (`X_std`).
   * Langkah ini krusial karena algoritma K-Means sangat sensitif terhadap perbedaan skala satuan fitur.
   * Visualisasi distribusi dilakukan sebelum dan sesudah scaling menggunakan perbandingan `sns.kdeplot`.

---

## 📊 Penentuan Jumlah Cluster Optimal ($k$)

Tugas ini membandingkan dua pendekatan untuk menentukan jumlah cluster terbaik:

### 1. Metode Elbow Manual (Inertia / WSS)
* Dilakukan *looping* untuk nilai $k$ dari 1 sampai 10.
* Hasil visualisasi grafik penurunan nilai *Inertia* menunjukkan titik tekukan tajam (siku) yang landai pada angka **$k = 4$**.
* Hasil pengelompokan disimpan ke dalam dataframe dengan nama kolom `cluster_elbow`.

### 2. Metode Elbow Otomatis (Yellowbrick KElbowVisualizer)
* Menggunakan library `yellowbrick` dengan memanggil `KElbowVisualizer`.
* Visualisasi grafik *Distortion Via-Score Plot* secara otomatis mendeteksi kecenderungan optimalisasi fungsi jarak pada titik **$k = 3$**.
* Hasil pengelompokan berbasis visualisasi otomatis ini disimpan dengan nama kolom `cluster_via`.

---

## 📈 Evaluasi & Visualisasi Hasil Akhir
Pada sel terakhir notebook, dilakukan perbandingan visual antara hasil pembentukan kelompok (`cluster_via`) dengan sebaran pengelompokan dari anotator asli (`deskripsi`). 

Grafik perbandingan membuktikan bahwa kombinasi penentuan cluster $k=3$ melalui standarisasi fitur mampu memisahkan kelompok berat dan tinggi badan dengan batas-batas wilayah (*decision boundary*) yang sangat selaras dengan persepsi klasifikasi manual manusia.

---

## 🚀 Prasyarat & Library Pendukung
Guna menjalankan notebook ini tanpa kendala, pastikan paket-paket pustaka berikut sudah terinstal di lingkungan kerja Python Anda:

```bash
pip install numpy pandas seaborn matplotlib scikit-learn yellowbrick
