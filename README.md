# UAS-FINALTERM-FOR-MACHINE-LEARNING
Repo ini berisi file-file UAS (FINALTERM) FOR MACHINE LEARNING Telkom University


Repositori ini berisi **tiga proyek utama** dari mata kuliah **Machine Learning - Telkom University**(untuk detail ada di masing-masing folder):

1. **Deteksi Penipuan Transaksi Online** – memprediksi probabilitas transaksi online fraud menggunakan ML dan DL.  
2. **Klasifikasi Gambar Ikan** – mengklasifikasikan spesies ikan dari gambar menggunakan CNN dan transfer learning.  
3. **Prediksi Variabel Regresi Tabular** – membangun pipeline regresi untuk memprediksi nilai variabel target dari dataset tabular menggunakan ML dan MLP (deep learning).

---

# 💳 1. Deteksi Penipuan Transaksi Online

## Deskripsi Proyek
Pipeline end-to-end untuk memprediksi apakah transaksi online bersifat fraud. Meliputi preprocessing, feature engineering, pelatihan model ML & DL, evaluasi performa, dan visualisasi.

## Implementasi Teknis
- **Preprocessing**: imputasi median, label encoding, scaling, hapus fitur dengan >80% missing values  
- **Class Imbalance Handling**: SMOTE  
- **Model ML**: Logistic Regression, Random Forest, XGBoost, LightGBM  
- **Model DL**: Neural Network (Dense + BatchNorm + Dropout)  
- **Loss**: Binary Crossentropy, Optimizer: Adam  

## Evaluasi & Visualisasi
- **Metrics**: Accuracy, Precision, Recall, F1-Score, ROC-AUC  
- **Visualisasi**: distribusi kelas, missing values, training curves, ROC curve, confusion matrix, feature importance  

## Wawasan Utama
- Tantangan: class imbalance <5%, banyak missing values, fitur kompleks  
- Solusi: SMOTE, imputasi strategis, preprocessing sistematis  
- Best Practices: stratified split, no data leakage, early stopping, feature importance analysis  

---

# 🐟 2. Klasifikasi Gambar Ikan dengan CNN

## Deskripsi Proyek
Klasifikasi spesies ikan menggunakan **Custom CNN** dan **Transfer Learning** (VGG16, ResNet50, MobileNetV2). Meliputi augmentasi data, training, evaluasi performa, dan visualisasi fitur.

## Model yang Digunakan
- **Custom CNN**: 4 blok konvolusi (32 → 256), BatchNorm, Dropout, Dense(512 → 256 → num_classes), ~5–10 juta parameter  
- **VGG16 (Transfer Learning)**: Pre-trained ImageNet, top custom, ~15 juta parameter  
- **ResNet50 (Transfer Learning)**: Residual 50 layer, top custom, ~25 juta parameter  
- **MobileNetV2 (Transfer Learning)**: Lightweight, cepat, ~3.5 juta parameter  

## Implementasi Teknis
- **Augmentasi Data**: rescaling, rotasi ±20°, shift, shear, zoom, flip horizontal  
- **Optimizer**: Adam (lr=0.001), **Loss**: Categorical Crossentropy  
- **Callbacks**: EarlyStopping, ReduceLROnPlateau, ModelCheckpoint  

## Evaluasi
- **Metrics**: Accuracy, Top-3 Accuracy, Precision, Recall, F1-Score  
- **Visualisasi**: training/validation curves, confusion matrix, feature maps, perbandingan model  

## Wawasan Utama
- Data augmentation mencegah overfitting  
- Batch normalization mempercepat training  
- Transfer learning memanfaatkan knowledge ImageNet  
- Dropout meningkatkan generalisasi  
- Learning rate scheduling optimizes convergence  

---

# 📈 3. Prediksi Variabel Regresi Tabular

## Deskripsi Proyek
Pipeline regresi end-to-end untuk dataset tabular, mulai dari preprocessing, feature scaling, pemodelan ML & MLP, hingga evaluasi prediksi numerik.

## Implementasi Teknis
- **Preprocessing**: imputasi, scaling, encoding categorical  
- **Model ML**: Linear Regression, Random Forest Regressor  
- **Model DL**: MLP (Multilayer Perceptron) dengan 2–3 hidden layers, activation ReLU, dropout untuk regularisasi  
- **Loss**: Mean Squared Error (MSE), Optimizer: Adam  

## Evaluasi & Visualisasi
- **Metrics**: RMSE, MAE, R² Score  
- **Visualisasi**: prediksi vs actual, residual plots, feature importance (ML models), training loss curves (MLP)  

## Wawasan Utama
- Tantangan: fitur numerik berdimensi tinggi  
- Solusi: feature scaling, regularisasi, early stopping  
- Best Practices: train-test split 80-20, evaluasi komprehensif, residual analysis  

---

# 🎓 Hasil Pembelajaran
- Pipeline ML/DL end-to-end  
- Penanganan dataset nyata: missing values, imbalance, high dimensionality  
- Implementasi dan evaluasi ML & DL untuk klasifikasi & regresi  
- Feature engineering & selection  
- Transfer learning & fine-tuning untuk gambar  
- Visualisasi & interpretabilitas model  
- Best practices di computer vision & fraud detection  

# 🔮 Pengembangan Selanjutnya
- Hyperparameter tuning untuk ML & DL  
- Advanced feature engineering  
- Ensemble models  
- Anomaly detection  
- Model interpretability (SHAP/LIME)  
- Deployment real-time  

---



