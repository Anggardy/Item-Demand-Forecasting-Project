# 📊Store Item Demand Forecasting: XGBoost vs LSTM
Proyek ini merupakan analisis komparatif dalam memprediksi permintaan penjualan barang (Time Series Forecasting) menggunakan dua pendekatan yang berbeda: Machine Learning Tabular (XGBoost) dan Deep Learning Sekuensial (LSTM).

## 📝 Latar Belakang
Dalam industri ritel, memprediksi jumlah penjualan di masa depan sangat penting untuk manajemen inventaris. Proyek ini bertujuan untuk membandingkan performa arsitektur berbasis tree (XGBoost) yang ringan dan dapat diinterpretasikan, dengan arsitektur jaringan saraf tiruan (LSTM) yang dirancang khusus untuk menangkap pola sekuensial yang kompleks.

## 🛠️ Teknologi yang Digunakan
- Data: [Store Item Demand Forecasting Dataset](https://www.kaggle.com/datasets/dhrubangtalukdar/store-item-demand-forecasting-dataset)
- Bahasa: Python 3
- Manipulasi Data: Pandas, NumPy
- Machine Learning: Scikit-Learn, XGBoost
- Deep Learning: TensorFlow / Keras
- Visualisasi: Matplotlib

## 🧠 Metodologi & Arsitektur
### 1. Pendekatan XGBoost (Machine Learning)
- Akses dataset : menggunakan Dataset Kaggel
- Pengolahan data :
  - Mengubah format tanggal
  - Merangkum data penjualan
  - Memnambah fitur tahun, bulan, hari, dan hari dalam minggu (0 = Senin hingga 6 = Minggu)
  - Windowing : menggunakan teknik ACF & PCF untuk menentukan panjang window
  - Membagi data : 4 tahun pelatihan dan 1 tahun test
- Pelatihan model XGBoost:
  - n_estimators = 100
  - learning rate = 0.1
- Evaluasi

### 2. Pendekatan LSTM (Deep Learning)
- Akses dataset : menggunakan Dataset Kaggel
- Mengunci keacakan di tingkat library, Numpy, dan TensorFlow
- Pengolahan data :
  - Mengubah format tanggal
  - Merangkum data penjualan
  - Memnambah fitur tahun, bulan, hari, dan hari dalam minggu (0 = Senin hingga 6 = Minggu)
  - Windowing : menggunakan teknik Sliding window dengan jumlah timestep 7
  - Membagi data : 4 tahun pelatihan dan 1 tahun test
- Membangun model sederhana
- Penggunaan Callback (Optional)
- Evaluasi

## 📈 Hasil Evaluasi
- XGBoost Menghasilkan nilai MAPE sebesar **0.1%**
- LSTM Menghasilkan nilai MAPE sebesar **2.03%**
