# Lab Report: Feature Engineering Mastery
**Machine Learning Journey - Week 3**

Proyek ini mendokumentasikan proses *preprocessing* data menggunakan berbagai teknik **Feature Engineering** untuk meningkatkan kualitas model Machine Learning. Seluruh tahapan didasarkan pada implementasi Python menggunakan library `pandas`, `sklearn`, dan `feature-engine`.

##  Alur Pemrosesan Data

### 1.  Handling Duplicates
Langkah awal untuk menjaga integritas data dengan memastikan tidak ada baris yang berulang.
* **Metode**: Membandingkan `len(df)` sebelum dan sesudah `drop_duplicates()`.
* **Dataset**: `titanic.xlsx`.

### 2.  Outlier Handling (Penanganan Pencilan)
Mengelola data ekstrem agar tidak merusak distribusi statistik:
* **Interquartile Range (IQR)**: Menghitung batas *Lower* dan *Upper* pada dataset California.
* **Arbitrary Outlier Capper**: Teknik berbasis perspektif bisnis untuk membatasi nilai umur pada dataset Titanic (Rentang 3 - 80 tahun).


[Image of interquartile range box plot explanation]


### 3. Missing Value Management
Mengisi kekosongan data dengan strategi yang robust:
* **Threshold 20%**: Kolom dengan data hilang > 20% (seperti `Revenue`) akan dihapus.
* **Imputasi**:
    * **Numerik**: Menggunakan **Median** (Contoh: Kolom `Rating`).
    * **Kategorikal**: Menggunakan **Modus**.


### 4. Encoding & Scaling (Transformasi Fitur)
Menerjemahkan data kategori dan menyamakan skala angka:
* **One-Hot Encoding (OHE)**: Digunakan untuk fitur non-ordinal seperti `gender`.
* **Label Encoding**: Mengubah data kategorikal biner menjadi numerik (0 dan 1).
* **Feature Scaling**: Mengimplementasikan `StandardScaler` dan `MinMaxScaler` pada kolom `tenure` dan `MonthlyCharges`.


## Assignment Log

Berikut adalah ringkasan solusi untuk *assignment* yang diberikan:

| No | Assignment | Deskripsi Tindakan |
| :-- | :--- | :--- |
| **1.a** | **Outlier Detection** | Looping visualisasi (Histogram & Boxplot) pada kolom `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, dan `AveOccup`. |
| **1.b** | **IQR Handling** | Melakukan *capping* outlier khusus pada kolom `AveBedrms` dan memvalidasi ulang distribusinya. |
| **2** | **Missing Value** | Analisis kolom `Headquarters`. Ditemukan missing value ~4.61% (di bawah batas 20%), maka ditangani dengan **Imputasi Modus**. |
| **3.a** | **Label Encoding** | Membersihkan data `No internet service` menjadi `No` pada dataset Telco Churn, lalu melakukan transformasi ke format numerik. |


## Requirement
Instalasi library yang diperlukan untuk menjalankan notebook:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn feature-engine openpyxl

Dibuat oleh  : Mr.Josan Mauritz Sharon Nunuhitu Engineering
Mata Kuliah: Machine Learning (Week 3)

Status: Selesai :)



