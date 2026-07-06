# 🗑️ Image Classification using Transfer Learning
## Deteksi Jenis Sampah di Sekitar Kampus

## Deskripsi Proyek
Proyek ini merupakan implementasi **Image Classification** menggunakan metode **Transfer Learning** dengan model **ResNet50** untuk mengklasifikasikan enam jenis sampah di sekitar kampus.

Model dibangun menggunakan TensorFlow dan Keras dengan memanfaatkan bobot pre-trained ImageNet sehingga proses pelatihan menjadi lebih cepat dan menghasilkan akurasi yang lebih baik dibandingkan membangun model dari awal.

---

## Dataset

Dataset yang digunakan berasal dari Kaggle:

https://www.kaggle.com/datasets/farzadnekouei/trash-type-image-dataset

Dataset terdiri dari 6 kelas:

- Cardboard
- Glass
- Metal
- Paper
- Plastic
- Trash

Jumlah total gambar sekitar **2527 image**.

---

## Tujuan

Membangun model klasifikasi citra yang mampu mengenali jenis sampah secara otomatis menggunakan teknik Transfer Learning sehingga dapat membantu proses pemilahan sampah.

---

## Teknologi yang Digunakan

- Python
- TensorFlow 2.x
- Keras
- Matplotlib
- NumPy

---

## Arsitektur Model

Model menggunakan **ResNet50** sebagai feature extractor dengan konfigurasi berikut:

- Input Image : 224 × 224 × 3
- Pre-trained Weights : ImageNet
- include_top = False
- Base Model dibekukan (Frozen Layer)
- GlobalAveragePooling2D
- Dropout 0.5
- Dense Output (Softmax)

Jumlah output:

6 kelas

---

## Teknik yang Digunakan

### 1. Transfer Learning

Menggunakan model ResNet50 yang telah dilatih pada dataset ImageNet sehingga proses pelatihan menjadi lebih cepat.

### 2. Data Augmentation

Untuk meningkatkan variasi data pelatihan digunakan:

- Random Flip
- Random Rotation
- Random Zoom

### 3. Dropout

Dropout sebesar 0.5 digunakan untuk mengurangi risiko overfitting.

### 4. Early Stopping

Training akan berhenti otomatis apabila validation loss tidak mengalami peningkatan selama beberapa epoch.

---

## Parameter Training

| Parameter | Nilai |
|-----------|--------|
| Image Size | 224 × 224 |
| Batch Size | 32 |
| Epoch | 20 |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Categorical Crossentropy |
| Metrics | Accuracy |

---

## Struktur Folder

```
Project
│
├── image classification.ipynb
├── README.md
│
└── TrashType_Image_Dataset
    ├── cardboard
    ├── glass
    ├── metal
    ├── paper
    ├── plastic
    └── trash
```

---

## Cara Menjalankan Program

1. Install library

```bash
pip install tensorflow matplotlib numpy scipy
```

2. Download dataset dari Kaggle.

3. Letakkan folder dataset pada direktori project.

4. Jalankan seluruh cell notebook secara berurutan.

5. Tunggu proses training hingga selesai.

6. Grafik Accuracy dan Loss akan ditampilkan setelah training selesai.

---

## Hasil

Model berhasil melakukan klasifikasi terhadap enam jenis sampah menggunakan metode Transfer Learning dengan ResNet50.

Teknik Data Augmentation, Dropout, dan Early Stopping membantu meningkatkan kemampuan generalisasi model serta mengurangi overfitting selama proses pelatihan.

---

## Kelebihan

- Training lebih cepat karena menggunakan Transfer Learning.
- Tidak memerlukan dataset yang sangat besar.
- Akurasi lebih baik dibandingkan melatih model dari awal.
- Mengurangi overfitting dengan Data Augmentation dan Dropout.

---

## Pengembangan Selanjutnya

Beberapa pengembangan yang dapat dilakukan:

- Fine Tuning seluruh layer ResNet50.
- Menambahkan lebih banyak data training.
- Deploy model ke aplikasi web menggunakan Flask.
- Deploy ke perangkat IoT menggunakan TensorFlow Lite.
- Menambahkan fitur prediksi gambar secara real-time menggunakan webcam.

---

## Author

Nama : Josan Mauritz Sharon Nunuhitu

Mata Kuliah : Machine Learning
Nim         : 4222301060
