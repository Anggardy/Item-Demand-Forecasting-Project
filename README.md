# 📊Store Item Demand Forecasting: XGBoost vs LSTM
Proyek ini merupakan analisis komparatif dalam memprediksi permintaan penjualan barang (Time Series Forecasting) menggunakan dua pendekatan yang berbeda: Machine Learning Tabular (XGBoost) dan Deep Learning Sekuensial (LSTM).

## 📝 Latar Belakang
Dalam industri ritel, memprediksi jumlah penjualan di masa depan sangat penting untuk manajemen inventaris. Proyek ini bertujuan untuk membandingkan performa arsitektur berbasis tree (XGBoost) yang ringan dan dapat diinterpretasikan, dengan arsitektur jaringan saraf tiruan (LSTM) yang dirancang khusus untuk menangkap pola sekuensial yang kompleks.

## 🛠️ Teknologi yang Digunakan
Bahasa: Python 3
Manipulasi Data: Pandas, NumPy
Machine Learning: Scikit-Learn, XGBoost
Deep Learning: TensorFlow / Keras
Visualisasi: Matplotlib

## 🧠 Metodologi & Arsitektur
### 1. Pendekatan XGBoost (Machine Learning)
Model berbasis pohon algoritma ini diformat untuk menerima data tabular (2D).
- Feature Engineering: Menggunakan fungsi shift() untuk membuat variabel historis (lag features) dari 1 hingga 7 hari sebelumnya.
- Ekstraksi Waktu: Menambahkan fitur waktu seperti hari, bulan, dan penanda akhir pekan (weekend indicator).
- Keunggulan: Sangat cepat dilatih, tahan terhadap outlier, dan menyediakan Feature Importance untuk interpretasi bisnis.

### 2. Pendekatan LSTM (Deep Learning)
Model jaringan saraf ini dirancang untuk memproses data berurutan dalam format 3D (Samples, Time Steps, Features).
- Scaling: Normalisasi wajib menggunakan MinMaxScaler (rentang 0-1) untuk mencegah ledakan loss/error komputasi (gradient explosion).
- Sliding Window: Memotong deret waktu menjadi "jendela" kecil yang bergerak maju.
- Inverse Transform: Mengembalikan hasil tebakan model (0-1) ke wujud nilai asli (volume penjualan) sebelum dievaluasi.
