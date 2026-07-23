# Klasifikasi Citra Bunga dengan Multi-Layer Perceptron (MLP)

Proyek Ujian Akhir Semester (UAS) mata kuliah **Pengolahan Citra Digital**. Proyek ini membangun model klasifikasi citra bunga ke dalam beberapa kelas menggunakan pendekatan *Multi-Layer Perceptron* (MLP) dari Scikit-learn, dengan citra sebagai fitur mentah (raw pixel) yang telah melalui tahap praproses.

## Informasi Mata Kuliah

| Keterangan       | Detail                                       |
|------------------|-----------------------------------------------|
| Nama             | Ikwan Sah Putra                                |
| NIM              | 24146013                                       |
| Mata Kuliah      | Pengolahan Citra Digital                       |
| Dosen Pengampu   | Teuku Riski Noviandy, S.Kom., M.Kom            |

## Ringkasan Proyek

Proyek ini mengimplementasikan alur kerja klasifikasi citra secara end-to-end, mulai dari pemuatan dataset, praproses citra, pelatihan model, hingga evaluasi dan visualisasi hasil prediksi. Seluruh tahapan diimplementasikan dalam Python menggunakan OpenCV untuk pengolahan citra dan Scikit-learn untuk pemodelan machine learning.

## Alur Kerja (Pipeline)

1. **Instalasi pustaka** — memasang seluruh dependency yang dibutuhkan.
2. **Import pustaka** — memuat OpenCV, NumPy, Matplotlib, dan modul-modul Scikit-learn.
3. **Persiapan dataset** — menentukan path dataset dan ukuran citra target (64×64 piksel).
4. **Pemuatan dan praproses data** — membaca citra per kelas, melakukan resize, dan flattening menjadi vektor fitur.
5. **Encoding label dan ekstraksi fitur** — mengonversi label kelas ke bentuk numerik dan menstandardisasi fitur.
6. **Pembagian data latih/uji** — membagi dataset menggunakan `train_test_split`.
7. **Pelatihan model** — membangun dan melatih `MLPClassifier`.
8. **Evaluasi model** — menghitung akurasi, classification report, dan confusion matrix.
9. **Visualisasi hasil prediksi** — menampilkan contoh prediksi model terhadap data uji.

## Struktur Direktori

```
.
├── archive/
│   └── flowers/              # Dataset citra bunga (per subfolder = per kelas)
├── notebook/                 # Notebook / skrip proyek
├── Laporan_UAS_Pengolahan_Citra_Digital.docx
└── README.md
```

> Struktur dataset mengikuti pola `archive/flowers/<nama_kelas>/<file_citra>`, di mana nama subfolder menjadi label kelas secara otomatis.

## Dependensi

| Pustaka         | Kegunaan                                        |
|-----------------|--------------------------------------------------|
| `opencv-python` | Pembacaan dan praproses citra (resize dsb.)      |
| `numpy`         | Operasi numerik dan manipulasi array citra       |
| `matplotlib`    | Visualisasi citra dan hasil prediksi             |
| `scikit-learn`  | Split data, standardisasi, model MLP, evaluasi   |

## Instalasi

```bash
pip install opencv-python numpy matplotlib scikit-learn
```

## Cara Menjalankan

1. Unduh dan ekstrak dataset bunga ke dalam direktori `archive/flowers`.
2. Sesuaikan variabel `DATASET_PATH` dan `IMG_SIZE` pada skrip/notebook sesuai lokasi dataset.
3. Jalankan skrip/notebook secara berurutan mengikuti alur kerja di atas.
4. Hasil evaluasi (akurasi, classification report, confusion matrix) serta visualisasi prediksi akan ditampilkan pada output.

## Konfigurasi Utama

```python
DATASET_PATH = "archive/flowers"   # Path dataset
IMG_SIZE = 64                      # Ukuran citra setelah di-resize (64x64 piksel)
```

## Metodologi Singkat

- Setiap citra diubah ukurannya menjadi **64×64 piksel**, kemudian di-*flatten* menjadi vektor satu dimensi sebagai fitur masukan model.
- Label kelas diambil langsung dari nama subfolder dataset dan dikonversi ke bentuk numerik menggunakan `LabelEncoder`.
- Fitur distandardisasi menggunakan `StandardScaler` agar berada pada skala yang seragam.
- Data dibagi menjadi data latih dan data uji menggunakan `train_test_split`.
- Model klasifikasi menggunakan `MLPClassifier` (jaringan saraf tiruan sederhana / *feed-forward neural network*).

## Evaluasi

Performa model diukur menggunakan:
- **Accuracy score** — proporsi prediksi yang benar terhadap keseluruhan data uji.
- **Classification report** — precision, recall, dan F1-score per kelas.
- **Confusion matrix** — visualisasi sebaran prediksi benar/salah antar kelas dalam bentuk heatmap.

## Pengembangan Lebih Lanjut

- Menggunakan ekstraksi fitur yang lebih representatif (mis. HOG, histogram warna HSV) dibanding fitur piksel mentah.
- Menerapkan arsitektur *Convolutional Neural Network* (CNN) untuk potensi peningkatan akurasi.
- Melakukan augmentasi data guna memperkaya variasi citra pada data latih.

## Dokumen Terkait

Laporan lengkap beserta pembahasan setiap tahapan tersedia pada berkas:
`Laporan_UAS_Pengolahan_Citra_Digital.docx`
