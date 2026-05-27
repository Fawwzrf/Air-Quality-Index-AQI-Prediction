# 🌍 Air Quality Index (AQI) Prediction in Indian Cities

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626)

Proyek Air Quality Index (AQI) Prediction adalah model *machine learning* untuk menganalisis dan memprediksi tingkat kualitas udara harian di berbagai kota di India berdasarkan data polutan. Proyek ini dibangun menggunakan Python dan Scikit-Learn dengan mengimplementasikan algoritma seperti Linear Regression dan Random Forest.

---

### 👨‍💻 Identitas
* **Nama/NIM:** Fawwaz Aufa Al Ghautsa Rafi / H1D023097
* **Institusi:** Informatika Universitas Jenderal Soedirman (Unsoed)

### 🚀 Metodologi (Gimana Cara Kerjanya?)
Kita menggunakan pendekatan Data Science dan Machine Learning yang terstruktur buat ngerjain proyek ini:

1. **Eksplorasi Data (EDA)**
   * Mengidentifikasi banyak variabel polutan yang distribusinya miring ke kanan (*right-skewed*).
   * Mendeteksi dan menganalisis *outlier* (lonjakan polusi ekstrem), tapi tetap dipertahankan biar modelnya makin *robust* (tangguh).
   * Menganalisis korelasi linear dan non-linear antara berbagai polutan terhadap skor AQI keseluruhan.

2. **Pembersihan Data (*Preprocessing & Feature Engineering*)**
   * **Missing Value Imputation:** Pakai metode gabungan buat data *time-series*, yaitu **Interpolasi Linear** buat data kosong yang jaraknya berdekatan, dan **Imputasi Median** buat *gap* yang lebih besar biar nggak bias gara-gara *outlier*.
   * **Nanganin Data Miring (*Skewness*):** Pakai transformasi logaritma **(log1p)** buat menormalkan fitur numerik yang *right-skewed* (kayak NO2 dan PM2.5).
   * **Categorical Encoding:** Pakai **Target Encoding** buat kolom `City` (yang ada 26 kategori) biar bisa nangkap tren polusi per daerah tanpa bikin dimensi datanya meledak.
   * **Fitur Waktu:** Ngekstrak fitur `Bulan` dan `Hari` buat nangkap pola polusi musiman.

3. **Pemodelan & Evaluasi**
   * Bikin model *baseline* pakai **Linear Regression** buat patokan awal (dapat $R^2 \approx 0.73$).
   * Mengembangkan dan men-*tune* **Random Forest Regressor** buat nangkap hubungan yang lebih kompleks dan non-linear di dalam data lingkungan.

### 📊 Hasil & Insight
* **Performa Kece:** Model Random Forest berhasil tembus **$R^2$ Score 0.91** dengan **Mean Absolute Error (MAE) di angka 20.87**, jauh ngalahin model *baseline* regresi linear!
* **Fitur Paling Ngaruh:** `PM2.5` dan `CO` (Karbon Monoksida) teridentifikasi sebagai dalang utama yang paling bikin nilai AQI naik-turun.
* **Insight Kebijakan:** Kebijakan tata kota dan kontrol emisi harus memprioritaskan pengurangan partikel PM2.5 dan CO secara ketat kalau mau kesehatan masyarakat cepat membaik.

### 📂 Struktur Repositori
* `AQI_Prediction_Analysis.ipynb`: File utama Jupyter Notebook yang isinya *end-to-end code*, mulai dari tarik data, EDA, sampai *training* dan evaluasi model.

### 🚀 Cara Menjalankan (*How to Run*)
1. *Clone* repositori ini ke lokal kamu:
   ```bash
   git clone [https://github.com/Fawwzrf/India-Air-Quality-Prediction.git](https://github.com/Fawwzrf/India-Air-Quality-Prediction.git)
