# Image Classification Model - Tomato Leaf Disease

Ini adalah proyek klasifikasi citra berbasis deep learning yang dikembangkan sebagai bagian dari submission course **Belajar Pengembangan Machine Learning** di Dicoding. Proyek ini berhasil meraih **rating sempurna 5/5** dengan memenuhi seluruh kriteria yang ditetapkan.

---

## Fitur Tambahan yang Diimplementasikan

Model ini dikembangkan dengan memperhatikan beberapa aspek lanjutan berikut:

- Menggunakan **Callback** untuk kontrol pelatihan model.
- Gambar dataset memiliki **ukuran tidak seragam**.
- Dataset terdiri dari lebih dari **10.000 gambar**.
- Akurasi pada **training dan validation mencapai ≥95%**.
- Jumlah label yang diklasifikasikan lebih dari **3 kelas**.

---

##  Deskripsi Singkat Proyek

Tujuan dari proyek ini adalah membangun sistem klasifikasi otomatis untuk mendeteksi jenis penyakit pada daun tomat. Dataset berasal dari GitHub dan mencakup ribuan gambar daun tomat dalam berbagai kondisi.

---

## Dataset Overview

Dataset asli terdiri dari 14 tanaman dan 38 kelas penyakit. Namun, karena keterbatasan sumber daya, hanya gambar tanaman **tomat** yang digunakan.

Gambar telah diacak ukurannya untuk memenuhi kriteria resolusi tidak seragam, antara **200x200 hingga 256x256 piksel**.

### Distribusi Data (4 kelas terpilih)

| Label                          | Jumlah Gambar |
|--------------------------------|---------------|
| Tomato_Yellow_Leaf_Curl_Virus  | 5357          |
| Late_blight                    | 1909          |
| Spider_mites Two-spotted_spider_mite|1676      |
| Septoria_leaf_spot             | 1771          |
| **Total**                      | **10.713**    |

---

## Arsitektur Model

Model dibangun menggunakan **MobileNetV2** sebagai feature extractor dengan parameter yang dibekukan.

Tambahan layer:
- `Conv2D` (32 filters) + `ReLU` + `MaxPooling2D`
- `Conv2D` (64 filters) + `ReLU` + `MaxPooling2D`
- `Flatten` + `Dropout(0.5)` + `Dense(128)`
- Output layer dengan `softmax` untuk klasifikasi 4 kelas

Ukuran input: **150x150x3**

---

## Performa Model

Model menunjukkan performa pelatihan yang sangat stabil dan akurat.

| Epoch | Loss   | Accuracy | Val Loss | Val Accuracy |
|-------|--------|----------|----------|--------------|
| 1–10  | 0.0413 | 0.9895   | 0.0980   | 0.9683       |

---

## Evaluasi Prediksi

| Gambar | Label Asli                    | Prediksi Model                  |
|--------|-------------------------------|---------------------------------|
| 1      | Spider_mites Two-spotted_spider_mite| Spider_mites Two-spotted_spider_mite|
| 2      | Late_blight                   | Late_blight                     |
| 3      | Septoria_leaf_spot           | Septoria_leaf_spot              |
| 4      | Tomato_Yellow_Leaf_Curl_Virus| Tomato_Yellow_Leaf_Curl_Virus   |

---


