# Proyek End-to-End Deteksi Penipuan Menggunakan Machine Learning

## 📋  Proyek
Proyek ini membangun pipeline machine learning lengkap untuk memprediksi probabilitas sebuah transaksi online bersifat penipuan. Solusi mencakup algoritma machine learning tradisional dan pendekatan deep learning, lengkap dengan pra-pemrosesan data, rekayasa fitur, dan evaluasi model secara menyeluruh.

## 🎯 Tujuan Utama
Mendesain dan mengimplementasikan pipeline end-to-end (ML & DL) yang dapat memprediksi probabilitas transaksi online menjadi penipuan dengan akurasi dan keandalan tinggi.

## 👤 Informasi Mahasiswa
- **Nama**: Elieser Pasaribu
- **NIM**: 1103223209
- **Mata Kuliah**: Machine Learning - Telkom University  
- **Tugas**: UAS (Ujian Akhir Semester) - Individu  

## 📊 Deskripsi Dataset

### Dataset Training (`train_transaction.csv`)
- Berisi data transaksi berlabel untuk pelatihan dan evaluasi model  
- Setiap baris mewakili satu transaksi dengan berbagai fitur:
  - Jumlah transaksi  
  - Informasi waktu  
  - Kode produk  
  - Informasi kartu  
  - Detail alamat  
  - Label biner `isFraud` (1 = penipuan, 0 = sah)

### Dataset Test (`test_transaction.csv`)
- Berisi transaksi tanpa label dengan kolom fitur sama (tanpa `isFraud`)  
- Digunakan untuk menghasilkan prediksi probabilitas penipuan  
- Format output: `(TransactionID, probabilitas isFraud)`

## 🔧 Implementasi Teknis

### 1. Pra-Pemrosesan Data
- **Penanganan Nilai Hilang**: Median untuk fitur numerik, label encoding untuk fitur kategorikal  
- **Encoding Fitur**: Label encoding untuk kategori dengan penanganan data baru  
- **Normalisasi Fitur**: StandardScaler untuk fitur numerik  
- **Seleksi Fitur**: Menghapus fitur dengan >80% nilai hilang  

### 2. Penanganan Ketidakseimbangan Kelas
- **Metode**: SMOTE (Synthetic Minority Over-sampling Technique)  
- **Tujuan**: Menyeimbangkan dataset deteksi penipuan yang sangat tidak seimbang  
- **Hasil**: Sensitivitas model terhadap kasus penipuan meningkat  

### 3. Model Machine Learning

#### Model Tradisional:
1. **Logistic Regression**
   - Baseline classifier linear  
   - Cepat dilatih dan di-infer  
   - Koefisien mudah diinterpretasikan  

2. **Random Forest**
   - Ensemble dari decision tree  
   - Analisis pentingnya fitur  
   - Tahan terhadap overfitting  

3. **XGBoost**
   - Framework gradient boosting  
   - Performa tinggi pada data terstruktur  
   - Regularisasi bawaan  

4. **LightGBM**
   - Gradient boosting cepat  
   - Efisien memori  
   - Cocok untuk dataset besar  

#### Model Deep Learning:
5. **Neural Network**
   - **Arsitektur**:  
     - Input → Dense(256) → BatchNorm → Dropout(0.3)  
     - Dense(128) → BatchNorm → Dropout(0.3)  
     - Dense(64) → BatchNorm → Dropout(0.2)  
     - Dense(32) → Dropout(0.2)  
     - Output: Dense(1, sigmoid)  
   - Optimizer: Adam (lr=0.001)  
   - Loss: Binary Crossentropy  
   - Callbacks: EarlyStopping, ReduceLROnPlateau  

### 4. Metode Evaluasi
Semua model dievaluasi menggunakan:  
- **Accuracy**: Kebenaran keseluruhan  
- **Precision**: Proporsi prediksi positif yang benar  
- **Recall**: Proporsi positif sebenarnya yang terdeteksi  
- **F1-Score**: Harmonic mean antara precision dan recall  
- **ROC-AUC**: Area di bawah kurva ROC (metrik utama)  
- **Confusion Matrix**: Rincian prediksi model  



## 📊 Visualisasi yang Disertakan
- **Distribusi Kelas**: Diagram batang dan pie chart untuk transaksi penipuan vs sah  
- **Nilai Hilang**: Bar chart horizontal fitur dengan data hilang  
- **Riwayat Pelatihan**: Kurva loss, akurasi, AUC, precision, dan recall (Neural Network)  
- **Perbandingan Model**: Bar chart semua metrik antar model  
- **Kurva ROC**: Kurva ROC komparatif untuk semua model  
- **Confusion Matrix**: Heatmap prediksi tiap model  
- **Feature Importance**: 20 fitur terpenting (Random Forest)  

---

## 🔍 Insight Utama

### Tantangan yang Diatasi
- **Ketidakseimbangan Kelas**: Kasus penipuan biasanya <5%  
  **Solusi**: Teknik oversampling SMOTE  

- **Data Hilang**: Banyak fitur memiliki nilai hilang signifikan  
  **Solusi**: Imputasi strategis dan seleksi fitur  

- **Kompleksitas Fitur**: Ratusan fitur dengan tipe berbeda-beda  
  **Solusi**: Pipeline pra-pemrosesan sistematis  

- **Pemilihan Model**: Menemukan keseimbangan antara performa dan interpretabilitas  
  **Solusi**: Bandingkan beberapa algoritma dan pilih berdasarkan ROC-AUC  

### Praktik Terbaik yang Diterapkan
- ✅ Stratified train-validation split untuk mempertahankan distribusi kelas  
- ✅ Pra-pemrosesan terpisah untuk data train dan test (menghindari data leakage)  
- ✅ Penanganan kategori baru pada data test  
- ✅ Evaluasi menyeluruh dengan berbagai metrik  
- ✅ Analisis pentingnya fitur untuk interpretabilitas  
- ✅ Early stopping dan pengurangan learning rate untuk deep learning  
- ✅ Penanganan data tidak seimbang secara tepat  

---

## 🎓 Hasil Pembelajaran
Melalui proyek ini, keterampilan berikut dikembangkan:
- Membangun pipeline ML end-to-end dari data mentah hingga prediksi  
- Menangani tantangan data nyata (missing values, ketidakseimbangan, dll.)  
- Implementasi berbagai algoritma ML dan DL  
- Teknik evaluasi dan perbandingan model  
- Strategi rekayasa dan seleksi fitur  
- Desain arsitektur model deep learning  
- Prosedur validasi dan pengujian yang tepat  

---

## 🔮 Pengembangan Selanjutnya
Beberapa peningkatan yang dapat dilakukan:
- **Hyperparameter Tuning**: Grid/Random search untuk menemukan parameter optimal  
- **Rekayasa Fitur Lanjut**: Membuat fitur interaksi dan berbasis waktu  
- **Metode Ensemble**: Menggabungkan prediksi dari beberapa model  
- **Deteksi Anomali**: Implementasi metode unsupervised seperti Isolation Forest  
- **Interpretabilitas Model**: Menambahkan SHAP atau LIME untuk penjelasan model  
- **Deployment Produksi**: Membuat API untuk deteksi penipuan secara real-time  

---

 

