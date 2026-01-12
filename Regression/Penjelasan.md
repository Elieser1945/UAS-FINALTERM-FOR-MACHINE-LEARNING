# End-to-End Regression: Prediksi Tahun Rilis Lagu

## 📋  Proyek
Proyek ini membangun pipeline regresi menyeluruh untuk memprediksi tahun rilis sebuah lagu berdasarkan fitur audio. Berbagai algoritma machine learning dan deep learning dibandingkan untuk menemukan model terbaik dalam tugas regresi ini.

## 🎯 Tujuan Utama
Mendesain dan mengimplementasikan pipeline regresi end-to-end (menggunakan machine learning dan deep learning) yang mampu memprediksi tahun rilis lagu dengan akurasi tinggi dari karakteristik audio.

## 👤 Informasi Mahasiswa
- **Nama**: Elieser Pasaribu   
- **NIM**: 1103223209  
- **Mata Kuliah**: Machine Learning - Telkom University  
- **Tugas**: UAS (Ujian Akhir Semester) - Individu  

## 📊 Deskripsi Dataset
### Dataset: `midterm-regresi-dataset.csv`
- **Struktur**: Setiap baris mewakili satu lagu  
- **Variabel Target**: Kolom pertama - Tahun rilis (contoh: 2001, 1995)  
- **Fitur**: 90 kolom sisanya - Karakteristik audio  
  - Fitur timbre  
  - Properti akustik  
  - Ciri sinyal musik lainnya  
  - Nama fitur: feature_1, feature_2, ..., feature_90  

Nilai fitur audio bersifat numerik dan menggambarkan berbagai aspek suara, meski tidak mudah diinterpretasikan secara langsung oleh manusia.

## 🔧 Implementasi Teknis
### 1. Pra-pemrosesan Data
- **Normalisasi Fitur**: StandardScaler  
- **Pembagian Data**: 80-20 untuk train-test  
- **Deteksi Outlier**: Metode IQR, menjaga semua tahun valid  
- **Cek Nilai Hilang**: Memastikan integritas data  

### 2. Model Regresi yang Digunakan
#### Machine Learning Tradisional:
1. **Linear Regression** – model baseline, cocok untuk hubungan linear, cepat & mudah diinterpretasikan  
2. **Ridge Regression (L2)** – regularisasi untuk mengurangi overfitting, baik untuk fitur berkorelasi, alpha = 1.0  
3. **Lasso Regression (L1)** – memungkinkan seleksi fitur, solusi sparsity, alpha = 0.1  
4. **Random Forest Regressor** – ensemble dari decision tree, analisis pentingnya fitur, 100 estimator, max_depth=15  
5. **XGBoost Regressor** – gradient boosting, performa tinggi, regularisasi bawaan  
6. **LightGBM Regressor** – gradient boosting cepat, efisien untuk dataset besar, penggunaan memori rendah  

#### Deep Learning:
7. **Neural Network**  
   - **Arsitektur**:
     - Input → Dense(256) → BatchNorm → Dropout(0.3)  
     - Dense(128) → BatchNorm → Dropout(0.3)  
     - Dense(64) → BatchNorm → Dropout(0.2)  
     - Dense(32) → Dropout(0.2)  
     - Output: Dense(1)  
   - Optimizer: Adam (lr=0.001)  
   - Loss: MSE  
   - Callbacks: EarlyStopping, ReduceLROnPlateau  

### 3. Metode Evaluasi
Semua model dievaluasi menggunakan:  
- **MSE**: Rata-rata selisih kuadrat  
- **RMSE**: Akar MSE (dalam tahun)  
- **MAE**: Rata-rata selisih absolut (dalam tahun)  
- **R² Score**: Koefisien determinasi (proporsi variasi yang dijelaskan)  

**Metrik Utama**: R² Score (semakin tinggi semakin baik, 1.0 = prediksi sempurna)

## 🔍 Insight Utama

### Tantangan yang Diatasi
- **Dimensi Tinggi**: 90 fitur audio  
  **Solusi**: Normalisasi fitur dan teknik regularisasi

- **Hubungan Kompleks**: Pola non-linear antara audio dan tahun rilis  
  **Solusi**: Model berbasis pohon dan neural network

- **Pemilihan Model**: Menemukan keseimbangan optimal antara bias dan variance  
  **Solusi**: Perbandingan menyeluruh menggunakan berbagai metrik

### Praktik Terbaik yang Diterapkan
- ✅ Pembagian data train-test yang tepat (80-20)  
- ✅ Normalisasi fitur untuk model berbasis jarak  
- ✅ Perbandingan beberapa model  
- ✅ Evaluasi menggunakan metrik yang komprehensif  
- ✅ Analisis residual untuk diagnostik model  
- ✅ Interpretasi pentingnya fitur  
- ✅ Early stopping untuk mencegah overfitting  
- ✅ Visualisasi prediksi dan kesalahan

---

## 🎓 Hasil Pembelajaran
Melalui proyek ini, keterampilan berikut dikembangkan:

- Membangun pipeline regresi end-to-end dari data hingga prediksi  
- Mengelola data numerik berdimensi tinggi  
- Implementasi berbagai algoritma regresi  
- Deep learning untuk tugas regresi  
- Evaluasi model menggunakan metrik yang sesuai  
- Analisis residual dan diagnostik model  
- Interpretasi pentingnya fitur  
- Analisis perbandingan kinerja model

---

## 🔮 Pengembangan Selanjutnya
Peningkatan yang dapat dilakukan:

- **Hyperparameter Tuning**: Grid/Random search untuk menemukan parameter optimal  
- **Feature Engineering**: Membuat fitur polinomial dan interaksi antar fitur  
- **Ensemble Methods**: Stacking atau voting regressor  
- **Analisis Time-Series**: Mempertimbangkan pola temporal evolusi musik  
- **Arsitektur Neural Lanjut**: LSTM atau Transformer  
- **Cross-Validation**: K-fold CV untuk evaluasi lebih robust  
- **Seleksi Fitur**: Recursive feature elimination

