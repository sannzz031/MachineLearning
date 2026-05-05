# 🤖 Machine Learning Lab: Preprocessing, Regression & Classification

Repository ini berisi dokumentasi teknis dan implementasi praktis untuk mata kuliah **Machine Learning**. Proyek ini mencakup alur kerja lengkap dari pengolahan data mentah (*Feature Engineering*) hingga pembangunan model prediksi untuk harga rumah, klasifikasi keselamatan penumpang, dan prediksi gaji karyawan.

---

## 📁 Cakupan Proyek

### 1. 🧹 Feature Engineering & Preprocessing
Sebelum masuk ke pemodelan, dilakukan optimalisasi data untuk memastikan performa model yang maksimal:
* **Handling Duplicates**: Pembersihan baris ganda pada data Titanic.
* **Missing Value Strategy**: 
    * **Mean Imputation**: Mengisi nilai kosong pada `pengalaman_kerja`.
    * **Median Imputation**: Digunakan pada fitur `Rating`.
    * **Modus Imputation**: Digunakan pada fitur `Headquarters`.
* **Outlier Management**: 
    * **Metode IQR**: Digunakan pada *California Dataset* (Fitur `AveBedrms`).
    * **Metode Bisnis**: *Arbitrary Capping* pada data Titanic (Batas usia 3-80 tahun).
* **Data Encoding**: 
    * **Binary Encoding**: Jenis kelamin (Pria: 1, Wanita: 0).
    * **Ordinal Encoding**: Jenjang pendidikan (SMA < D3 < S1 < S2).
    * **Label Encoding**: Fitur layanan pada dataset Telco Churn.

### 2. 📈 Regression Analysis (USA Housing & Salary Prediction)
Implementasi model untuk memprediksi nilai kontinu:
* **USA Housing**: Memprediksi harga rumah dengan **R² Score: 0.919**.
* **Prediksi Gaji**: Membandingkan **Linear Regression** dan **Decision Tree Regressor**.
* **Metrik Evaluasi**: MAE (Mean Absolute Error), RMSE, dan R² Score (bukan Confusion Matrix karena ini adalah kasus Regresi).

### 3. 🎯 Classification (Titanic Survival)
Memprediksi tingkat kelangsungan hidup penumpang menggunakan berbagai algoritma:
* **Naive Bayes**: Memberikan hasil terbaik dengan akurasi **0.77**.
* **K-Nearest Neighbors (KNN)**: Dioptimalkan menggunakan **GridSearchCV**.
* **Optimization Results**: Parameter terbaik ditemukan menggunakan metric `manhattan` dengan `n_neighbors: 3`.

---

## 📊 Hasil Evaluasi & Visualisasi
Proyek ini menghasilkan berbagai visualisasi teknis untuk analisis model:
* **Correlation Heatmap**: Melihat hubungan antar fitur.
* **Residual Analysis**: Evaluasi error pada model regresi (pengganti Confusion Matrix).
* **Tree Structure**: Visualisasi struktur *Decision Tree* untuk transparansi model.
* **Actual vs Predicted Plot**: Melihat sejauh mana akurasi prediksi model terhadap data asli.

---

## 🚀 Requirement & Installation
Untuk menjalankan notebook atau script di repository ini, pastikan library berikut telah terinstal:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels scipy feature-engine openpyxl
