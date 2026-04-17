#  USA Housing Price Prediction
**Supervised Learning: Linear Regression Project**

Proyek ini bertujuan untuk membangun model prediksi harga rumah di Amerika Serikat menggunakan dataset `USA_Housing`. Melalui pendekatan **Supervised Learning**, model ini belajar dari data historis fitur perumahan untuk memprediksi nilai jual secara akurat.

---

## Alur Pengerjaan

### 1. Persiapan & Eksplorasi Data (EDA)
Langkah awal melibatkan pembersihan data dan pemahaman karakteristik dataset:
* **Dataset**: Terdiri dari 5.000 entri dengan fitur seperti pendapatan rata-rata area, usia rumah, jumlah kamar, dan populasi.
* **Cleaning**: Menghapus kolom `Address` karena merupakan data teks non-kategorikal yang tidak relevan untuk regresi numerik.
* **Visualisasi**: Menggunakan `pairplot` dan `correlation heatmap` untuk melihat hubungan antar variabel. Ditemukan bahwa **Avg. Area Income** memiliki korelasi terkuat dengan harga rumah.

### 2. Training Model
Proses pembangunan kecerdasan buatan:
* **Splitting**: Membagi data menjadi 70% Training dan 30% Testing untuk validasi yang objektif.
* **Algoritma**: Menggunakan **Linear Regression** dari library `Scikit-Learn`.
* **Interpretasi**:
    * **Intercept**: ~ -2,631,028
    * **Koefisien Terbesar**: `Avg. Area House Age` dan `Avg. Area Number of Rooms` memiliki pengaruh harga per unit yang paling signifikan.

### 3. Analisis Statistik (Signifikansi Fitur)
Melakukan *deep dive* pada kualitas setiap prediktor:
* **t-statistic**: Digunakan untuk mengukur stabilitas fitur. 
* **Insight**: Fitur `Avg. Area Number of Bedrooms` memiliki nilai t-statistik terkecil (2.33), menunjukkan kontribusinya tidak se-signifikan fitur pendapatan atau usia rumah dalam model ini.

### 4. Evaluasi & Uji Asumsi
Memastikan model valid dan tidak "asal tebak":
* **Uji Normalitas**: Menggunakan **Shapiro-Wilk Test** pada residual (p-value: 0.62). Karena p > 0.05, residual terdistribusi normal.
* **Homoskedastisitas**: Melalui plot *Residuals vs Predicted*, data tersebar merata tanpa pola tertentu, menunjukkan varians error yang stabil.
* **Metrik Performa**:
    * **R-Squared (Test)**: 0.919 (Model mampu menjelaskan 91.9% variansi data).
    * **MAE**: ~81,739 (Rata-rata kesalahan prediksi).

---

## Kesimpulan Model
Model ini sangat handal dengan skor **R² mencapai 0.92**. Meskipun terdapat sedikit outlier, secara umum model mampu memprediksi harga rumah dengan rata-rata kesalahan hanya sekitar 8% dari harga rata-rata keseluruhan.

---

## Library yang Digunakan
Pastikan library berikut sudah terinstal di lingkungan Python Anda:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels scipy

Dibuat oleh  : Mr.Josan Mauritz Sharon Nunuhitu Engineering
Nim          : 4222301060
Mata Kuliah: Machine Learning (Week 4)

Status: Selesai :)
