#  Klasifikasi Gambar Ikan dengan CNN

## 📌 Ringkasan Proyek
Proyek ini membangun pipeline **deep learning end-to-end** untuk mengklasifikasikan spesies ikan menggunakan **Convolutional Neural Networks (CNN)**. Pendekatan yang digunakan meliputi **CNN kustom** dan **transfer learning**, dengan tujuan mencapai akurasi tinggi pada klasifikasi multi-kelas.

## 👨‍🎓 Informasi Mahasiswa
- **Nama**: Elieser Pasaribu
- **NIM**: 1103223209
- **Institusi**: Telkom University
- **Tugas**: UAS (Ujian Akhir Semester)

## 📊 Informasi Dataset
Dataset terdiri dari gambar ikan yang terorganisir rapi dalam struktur folder


### Spesifikasi Gambar
- **Ukuran**: 224x224 piksel (standarisasi)  
- **Warna**: RGB (3 channel)  
- **Format**: JPEG / PNG  
- **Kelas**: Beragam spesies ikan  

## 🧠 Model yang Digunakan

### 1. **CNN Kustom**
CNN dibangun dari awal dengan:  
- 4 **Convolutional Block** (32 → 64 → 128 → 256 filter)  
- **Batch Normalization** setelah setiap conv layer  
- **MaxPooling** untuk mengurangi dimensi spasial  
- **Dropout**: 25% setelah conv block, 50% pada dense layer  
- **Dense Layer**: 512 → 256 → num_classes  
- **Parameter**: ±5–10 juta (tergantung jumlah kelas)  

## 2. VGG16 (Transfer Learning)
Pre-trained pada **ImageNet** dengan tambahan **top layer kustom**:

- **Base Model**: VGG16 (berat/frozen weights dibekukan)  
- **Feature Extractor**: 16 layer dengan konvolusi 3x3  
- **Top Layer Kustom**: GlobalAveragePooling → Dense(512) → Dense(256) → Softmax  
- **Jumlah Parameter**: ±15 juta (14.7M frozen, ~2M trainable)  
- **Kelebihan**: Ekstraksi fitur mendalam dari arsitektur yang terbukti kuat  

---

## 3. ResNet50 (Transfer Learning)
Residual Network dengan **skip connection** untuk mengatasi vanishing gradient:

- **Base Model**: ResNet50 (frozen weights)  
- **Inovasi**: Residual block yang memecahkan masalah vanishing gradient  
- **Top Layer Kustom**: GlobalAveragePooling → Dense(512) → Dense(256) → Softmax  
- **Jumlah Parameter**: ±25 juta (23.5M frozen, ~2M trainable)  
- **Kelebihan**: Sangat dalam (50 layer) tanpa degradasi performa  

---

## 4. MobileNetV2 (Transfer Learning)
Arsitektur efisien untuk deployment dan perangkat mobile:

- **Base Model**: MobileNetV2 (frozen weights)  
- **Inovasi**: Depthwise separable convolution (ringan)  
- **Top Layer Kustom**: GlobalAveragePooling → Dense(512) → Dense(256) → Softmax  
- **Jumlah Parameter**: ±3.5 juta (2.2M frozen, ~1.3M trainable)  
- **Kelebihan**: Inference cepat, ukuran model kecil, ramah untuk mobile

## 📈 Metrik Evaluasi

### Metrik Klasifikasi
- **Accuracy**: Proporsi prediksi yang benar terhadap total prediksi  
- **Top-3 Accuracy**: Apakah label asli termasuk dalam 3 prediksi teratas  
- **Precision**: TP / (TP + FP) untuk setiap kelas  
- **Recall**: TP / (TP + FN) untuk setiap kelas  
- **F1-Score**: Rata-rata harmonis dari precision dan recall  

### Visualisasi
- Kurva **accuracy** dan **loss** untuk data training dan validasi  
- **Confusion matrix** untuk semua model  
- Contoh prediksi dengan skor keyakinan (**confidence scores**)  
- Visualisasi **feature map** dari layer konvolusi  
- Grafik perbandingan performa antar model

## 🌟 Wawasan Utama (Key Insights)

### ⚡ Apa yang Berjalan dengan Baik
🎨 **Data augmentation** membantu mencegah overfitting  
🚀 **Batch normalization** mempercepat proses training  
🧠 **Transfer learning** memanfaatkan pengetahuan dari ImageNet  
🛡️ **Dropout** meningkatkan kemampuan generalisasi model  
⏱️ **Learning rate scheduling** mengoptimalkan konvergensi model  

### 🔧 Potensi Peningkatan
🛠️ **Fine-tuning** model transfer learning (membuka beberapa layer terakhir)  
🤝 **Metode ensemble** untuk menggabungkan prediksi dari beberapa model  
✨ **Augmentasi lanjutan** (CutMix, MixUp) untuk variasi data lebih banyak  
🎯 **Attention mechanism** untuk fokus pada area penting di gambar  
🖼️ **Resolusi gambar lebih tinggi** untuk menangkap detail lebih baik  

## 🎓 Hasil Pembelajaran (Learning Outcomes)
Melalui proyek ini, peserta mempelajari dan menerapkan:  
- 🐾 Pipeline CNN end-to-end untuk klasifikasi gambar  
- 🏗️ Prinsip desain arsitektur CNN custom  
- 🧩 Implementasi dan manfaat transfer learning  
- 🎨 Strategi augmentasi data untuk meningkatkan generalisasi  
- 📊 Evaluasi dan perbandingan performa model  
- 👁️ Visualisasi model deep learning untuk interpretabilitas  
- ✅ Praktik terbaik dalam computer vision

