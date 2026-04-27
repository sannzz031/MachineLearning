# 🤖 Machine Learning Journey: Week 3 Lab Report

Repository ini berisi dokumentasi lengkap pengerjaan praktikum Machine Learning minggu ketiga. Fokus utama materi adalah persiapan data (Preprocessing) dan implementasi model Supervised Learning (Regresi & Klasifikasi).

---

## 🛠️ Phase 1: Feature Engineering
Sebelum masuk ke pemodelan, data harus "dimasak" agar berkualitas tinggi. Berikut teknik yang diimplementasikan:

* **Handling Duplicates**: Memastikan integritas data dengan menghapus baris ganda pada dataset Titanic.
* **Outlier Management**: 
    * **Metode IQR**: Digunakan pada *California Dataset* untuk membatasi nilai ekstrem secara statistik.
    * **Metode Bisnis**: *Arbitrary Capping* pada data Titanic (Contoh: Membatasi usia 3-80 tahun).
* **Missing Value Strategy**: 
    * Imputasi **Median** untuk data numerik (Rating).
    * Imputasi **Modus** untuk data kategorikal.
    * Penghapusan kolom jika data hilang > 20% (Contoh: Kolom Revenue).
* **Feature Transformation**: 
    * **Encoding**: Mengubah teks ke angka via *One-Hot Encoding* dan *Label Encoding*.
    * **Scaling**: Menyamakan rentang data menggunakan *StandardScaler* dan *MinMaxScaler*.

---

## 📈 Phase 2: Supervised Learning - Regression
Memprediksi harga rumah menggunakan dataset **USA_Housing.csv**.

### Key Highlights:
* **Exploratory Data Analysis (EDA)**: Menemukan korelasi kuat antara `Avg. Area Income` terhadap `Price`.
* **Model Performance**:
    * **R-Squared (Test)**: **0.919** (Model mampu menjelaskan 91.9% variansi data).
    * **MAE**: ~81,739.
* **Statistical Analysis**: Menggunakan *t-statistic* untuk menguji signifikansi fitur. Ditemukan bahwa fitur jumlah kamar tidur memiliki pengaruh yang lebih kecil dibanding usia rumah.

---

## 🎯 Phase 3: Supervised Learning - Classification
Memprediksi kelangsungan hidup penumpang menggunakan dataset **Titanic.csv**.

### Perbandingan Model:
| Algoritma | Akurasi | Keterangan |
| :--- | :---: | :--- |
| **K-Nearest Neighbors** | 0.71 | Klasifikasi berbasis tetangga terdekat. |
| **Decision Tree** | 0.77 | Klasifikasi berbasis pohon keputusan. |
| **Naive Bayes** | **0.77** | Memberikan hasil probabilitas paling stabil di uji coba ini. |

### Optimization & Testing:
* **Hyperparameter Tuning**: Menggunakan `GridSearchCV` untuk mencari parameter terbaik pada KNN (ditemukan metric *manhattan* dengan *n_neighbors* 3 sebagai yang terbaik).
* **Prediksi Data Baru**: Model berhasil memprediksi probabilitas keselamatan penumpang baru (Kelas 3, Perempuan, 25 tahun) dengan hasil **Tidak Selamat** (94.5% probabilitas).

---

## 🛠️ Requirements & Installation
Untuk menjalankan notebook ini di lokal, pastikan library berikut sudah terinstal:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels scipy feature-engine openpyxl
📂 Struktur File
Feature_Engineering.ipynb - Log pembersihan dan transformasi data.

Regression_USA_Housing.ipynb - Prediksi harga rumah.

Classification_Titanic.ipynb - Klasifikasi keselamatan penumpang.

hasil_gridsearch_knn.xlsx - Output optimasi parameter model.

Project by: Josan Mauritz Sharon Nunuhitu

Engineering Student | Semester 6
