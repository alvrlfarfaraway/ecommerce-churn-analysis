# Ecommerce Customer Churn Analysis using Logistic Regression

Proyek ini berfokus pada prediksi probabilitas *churn* pelanggan menggunakan algoritma Regresi Logistik. Tantangan utama yang diselesaikan dalam proyek ini adalah penanganan data tidak seimbang (*imbalanced data*) serta identifikasi variabel yang paling berpengaruh terhadap keputusan pelanggan untuk berhenti berlangganan.

## Alur Kerja Proyek
Dataset diproses melalui beberapa tahap prapemrosesan mulai dari penanganan nilai yang hilang menggunakan median imputer hingga transformasi variabel kategorikal dengan One-Hot Encoding. Untuk mengatasi bias pada model, teknik SMOTE diterapkan guna menyeimbangkan kelas target sebelum masuk ke tahap pelatihan model.

## Analisis Heatmap Korelasi
Peta korelasi digunakan untuk mengukur kekuatan hubungan linear antar variabel numerik utama. Berdasarkan visualisasi ini, fitur **Complain** menunjukkan korelasi positif yang paling konsisten terhadap target Churn dibandingkan fitur numerik lainnya. Meskipun fitur kategorikal seperti status pernikahan tidak muncul dalam heatmap awal ini, instrumen ini sangat krusial untuk memastikan tidak adanya multikolinearitas yang ekstrem dalam dataset.

## Evaluasi Performa Model
Setelah penerapan teknik penyeimbangan data, model Regresi Logistik menghasilkan performa yang solid dengan akurasi sebesar 79.34%. Fokus utama evaluasi terletak pada nilai Recall kelas 1 yang mencapai 0.80, menandakan sensitivitas tinggi model dalam menangkap pelanggan yang asli akan *churn*. Selain itu, skor ROC-AUC sebesar 0.875 mengonfirmasi kemampuan diskriminasi yang sangat baik dalam memisahkan kelas pelanggan setia dan yang berisiko.

## Interpretasi Faktor Pemicu (Feature Importance)
Analisis koefisien model menunjukkan bahwa **MaritalStatus_Single** memiliki bobot tertinggi (1.4), disusul oleh **Complain** (0.4). Dominasi status pernikahan dalam koefisien ini dipengaruhi oleh skala variabel biner hasil *encoding* yang memerlukan bobot lebih besar untuk mendefinisikan garis keputusan. Secara strategis, **Complain** tetap menjadi area intervensi utama karena merupakan variabel perilaku yang dapat dikelola langsung oleh perusahaan untuk meningkatkan retensi pelanggan.

## Library yang Digunakan
* Pandas & Numpy
* Matplotlib & Seaborn
* Scikit-learn
* Imbalanced-learn (SMOTE)
