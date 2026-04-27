# 🤖 Machine Learning Lab: Preprocessing & Supervised Learning

Repository ini berisi dokumentasi teknis dan implementasi praktis untuk **Week 6: Machine Learning**. Proyek ini mencakup alur kerja lengkap dari pengolahan data mentah (*Feature Engineering*) hingga pembangunan model prediksi menggunakan algoritma Regresi dan Klasifikasi.

---

## 🛠️ Phase 1: Feature Engineering & Preprocessing
Sebelum masuk ke pemodelan, dilakukan optimalisasi data untuk memastikan performa model yang maksimal.

* **Duplicate Handling**: Pembersihan baris ganda pada dataset Titanic.
* **Missing Value Strategy**: 
    * Imputasi **Median** untuk data numerik (Contoh: Fitur `Rating` & `Age`).
    * Imputasi **Modus** untuk data kategorikal (Contoh: Fitur `Headquarters`).
    * *Drop Column* untuk fitur dengan kekosongan > 20% (Contoh: Fitur `Revenue`).
* **Outlier Management**: 
    * **Metode IQR**: Digunakan pada *California Dataset* (Fitur `AveBedrms`).
    * **Metode Bisnis**: *Arbitrary Capping* pada data Titanic (Membatasi usia 3-80 tahun).
* **Feature Transformation**: 
    * **Encoding**: *Label Encoding* & *One-Hot Encoding* untuk data kategorikal (`Sex`, `Embarked`, dll).
    * **Scaling**: Implementasi `StandardScaler` & `MinMaxScaler` pada fitur `tenure` dan `MonthlyCharges`.

---

## 📈 Phase 2: Regression (USA Housing Price)
Implementasi **Linear Regression** untuk memprediksi harga rumah.

* **Metrik Evaluasi**: 
    * **R-Squared (Test)**: **0.919** (Sangat Akurat).
    * **MAE**: ~81,739.
* **Insight Statistik**: Analisis *t-statistic* menunjukkan fitur `Avg. Area House Age` dan `Avg. Area Number of Rooms` memiliki pengaruh paling signifikan terhadap harga.


---

## 🎯 Phase 3: Classification (Titanic Survival)
Perbandingan berbagai algoritma untuk memprediksi tingkat kelangsungan hidup penumpang.

### 🏆 Model Comparison:
| Algoritma | Akurasi | Status |
| :--- | :---: | :--- |
| **Naive Bayes** | **0.77** | **Best Performance** |
| **K-Nearest Neighbors (KNN)** | 0.71 | Baseline |
| **Decision Tree** | 0.77 | Competitive |

### ⚙️ Optimization (GridSearchCV)
Dilakukan pencarian parameter terbaik untuk model KNN menggunakan 5-fold Cross Validation:
* **Best Params**: `{'metric': 'manhattan', 'n_neighbors': 3, 'weights': 'uniform'}`
* **Output**: Hasil optimasi disimpan secara otomatis ke dalam file `hasil_gridsearch_knn.xlsx`.

### 🔮 Prediksi Data Baru
Model berhasil memprediksi penumpang baru (Kelas 3, Perempuan, Usia 25) dengan probabilitas **94.5% Tidak Selamat** (Label 0).

---

## 🚀 Requirement & Installation
Untuk menjalankan notebook ini, pastikan library berikut telah terinstal:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels scipy feature-engine openpyxl0

📂 Struktur File
Feature_Engineering.ipynb - Log pembersihan dan transformasi data.

Regression_USA_Housing.ipynb - Prediksi harga rumah.

Classification_Titanic.ipynb - Klasifikasi keselamatan penumpang.

hasil_gridsearch_knn.xlsx - Output optimasi parameter model.

Project by: Josan Mauritz Sharon Nunuhitu

Engineering Student | Semester 6
