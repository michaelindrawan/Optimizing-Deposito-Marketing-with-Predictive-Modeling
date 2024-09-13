# JCDSOL_Machine-Learning

#### READ ME

## 1. Business Understanding

### 1.1 Konteks
- **Produk Keuangan**: Deposito berjangka adalah produk perbankan di mana nasabah menyimpan uang untuk periode tertentu dengan imbalan bunga tetap.
- **Kampanye Pemasaran**: Bank perlu memanfaatkan data pelanggan dan pemasaran untuk merancang kampanye yang efektif guna menarik dan mempertahankan nasabah.

### 1.2 Pernyataan Masalah
- **Tantangan**: Mengidentifikasi strategi pemasaran yang tepat untuk meningkatkan konversi nasabah dalam lingkungan perbankan yang kompetitif.

### 1.3 Tujuan
- **Tujuan**: Menganalisis data pelanggan dan pemasaran untuk mengidentifikasi pola dan tren, serta mengoptimalkan strategi pemasaran guna meningkatkan konversi nasabah baru untuk produk deposito berjangka.

## 2. Pendekatan Analisis

### 2.1 Pendekatan
- **Machine Learning**: Teknik klasifikasi digunakan untuk memprediksi kemungkinan nasabah melakukan deposito berjangka.
- **Langkah**: Mengumpulkan dan memproses data, melatih serta mengevaluasi model, dan mengidentifikasi nasabah potensial.

## 3. Metrik Evaluasi

Pendekatan analisis menggunakan machine learning untuk menentukan nasabah potensial dalam kampanye pemasaran melibatkan model klasifikasi. Evaluasi kinerja dilakukan menggunakan metrik berikut:

### Metrik Evaluasi
- **True Positive (TP)**: Nasabah yang diprediksi dan benar-benar melakukan deposito.
- **False Positive (FP)**: Nasabah yang diprediksi melakukan deposito tetapi tidak melakukannya.
- **True Negative (TN)**: Nasabah yang diprediksi tidak melakukan deposito dan benar-benar tidak melakukannya.
- **False Negative (FN)**: Nasabah yang diprediksi tidak melakukan deposito tetapi sebenarnya melakukannya.

### Akurasi (Accuracy)
**Definisi**: Proporsi dari total prediksi yang benar (baik positif maupun negatif).

**Contoh**: Jika model memprediksi 80 nasabah benar-benar melakukan deposito dan 10 nasabah benar-benar tidak melakukan deposito dari 100 prediksi, maka akurasi adalah 90%.

### Precision
**Definisi**: Proporsi dari semua prediksi positif yang benar-benar positif.

**Contoh**: Jika model memprediksi 80 nasabah sebagai potensial dan 20 nasabah tidak melakukannya, maka precision adalah 80%.

### Recall
**Definisi**: Proporsi dari semua nasabah yang benar-benar positif yang berhasil diprediksi.

**Contoh**: Jika model berhasil mendeteksi 80 dari 90 nasabah yang benar-benar melakukan deposito, maka recall adalah 89%.

### F1-Score
**Definisi**: Harmonik rata-rata dari precision dan recall, memberikan ukuran keseimbangan antara keduanya.

**Contoh**: Dengan precision 80% dan recall 89%, F1-Score adalah sekitar 84%.

## 4. Pemahaman Data

### 4.1 Profil Pelanggan
- **Atribut**: Usia, pekerjaan, saldo tabungan, status perumahan, pinjaman.

### 4.2 Data Pemasaran
- **Atribut**: Jenis komunikasi, bulan terakhir kontak, jumlah kontak, hasil kampanye sebelumnya.

### 4.3 Tujuan Analisis
- **Identifikasi Pola**: Menemukan pola dalam data.
- **Persiapan Data**: Menyiapkan data untuk model machine learning.
- **Prediksi**: Memprediksi nasabah potensial untuk deposito berjangka.

## 5. Pembersihan Data

- **Saldo Negatif**: Mengubah nilai negatif pada kolom balance menjadi 0 untuk konsistensi data.
- **Data Kosong**:
  - Mengganti nilai 'unknown' menjadi NaN pada kolom job dan menghapusnya. Memperbarui poutcome menjadi np.nan jika contact tidak 'unknown'.
  - Nilai -1 pada kolom pdays menunjukkan bahwa klien belum pernah dihubungi.
- **Imputasi Data**: Mengisi nilai hilang pada kolom kategorikal dengan modus setelah memeriksa distribusi nilai.
- **Visualisasi Missing Data**: 
  - Menggunakan `msno.heatmap(df)` dan `msno.dendrogram(df)` untuk memeriksa pola nilai hilang.
- **Analisis Keterkaitan Kolom**:
  - Memeriksa hubungan antara kolom dengan nilai hilang dan kolom kategorikal menggunakan uji Chi-square.
- **Matriks Korelasi**:
  - Menampilkan matriks korelasi untuk fitur numerik dan dummy variabel deposit.
- **Penghapusan Duplikat**: Menghapus entri duplikat, mengurangi jumlah dari 16 menjadi 0.

## 6. Analisis Data

### 6.1 Korelasi dan Visualisasi
- **Matriks Korelasi**: Menghitung dan menampilkan matriks korelasi untuk fitur numerik.
- **Visualisasi**: Menggunakan heatmap untuk menunjukkan hubungan antar fitur.

### 6.2 Asosiasi Variabel Kategorikal
- **Uji Chi-Square**: Evaluasi asosiasi antara kolom kategorikal dan kolom deposit.

### 6.3 Imputasi Data
- **Pendekatan Imputasi**: Mengisi nilai hilang berdasarkan modus kategori terkait.

## 7. Persiapan Data

### 7.1 Pembagian Data
- **Pembagian Dataset**: Membagi dataset menjadi data pelatihan dan pengujian dengan proporsi 75%-25% untuk melatih dan menguji model.

### 7.2 Transformasi Data
- **One-Hot Encoding**: Mengubah fitur kategorikal menjadi format numerik.
- **Robust Scaling**: Mengubah skala fitur numerik untuk mengurangi pengaruh nilai ekstrem.

### 7.3 Penghitungan VIF
- **Multikolinearitas**: Menghitung Variance Inflation Factor (VIF) untuk mengidentifikasi fitur dengan multikolinearitas tinggi dan menghapus fitur yang melebihi ambang batas yang disesuaikan.

### 7.4 Korelasi Fitur
- **Korelasi Fitur**: Menghitung dan menampilkan matriks korelasi untuk memahami hubungan antara fitur dan target dalam dataset pelatihan melalui heatmap.

## 8. Definisi Model dan Pengaturan Parameter

### 8.1 Jenis Model
- **Logistic Regression (Logreg)**
- **K-Nearest Neighbors (KNN)**
- **Decision Tree Classifier (DTC)**
- **Random Forest Classifier (RF)**
- **XGBoost Classifier (XGB)**
- **Support Vector Classifier (SVC)**

### 8.2 Parameter
- **Logreg**: Jenis penalti (l1, l2) dan kekuatan regularisasi (C).
- **KNN**: Jumlah tetangga, jenis bobot, dan metrik jarak (p).
- **DTC**: Kriteria (gini), kedalaman maksimum, dan pembagian/leaves sampel.
- **RF**: Jumlah estimator, kriteria, dan kedalaman maksimum.
- **XGB**: Jumlah estimator, laju pembelajaran, dan kedalaman maksimum.

## 9. Pelatihan dan Evaluasi Model

### 9.1 Pencarian Grid untuk Penyetelan Hyperparameter
- **Fungsi**: `grid_train`
- **Tujuan**: Menemukan parameter terbaik untuk setiap model.
- **Proses**:
  - Mengiterasi setiap model dan parameter grid-nya.
  - Menggunakan GridSearchCV dengan `neg_log_loss` dan cross-validation 5-lipat.
  - Menyimpan model terbaik, parameter, dan skor dalam DataFrame.

### 9.2 Pelatihan Model Ensemble
- **Fungsi**: `ensemble_train`
- **Tujuan**: Membangun model ensemble menggunakan Voting Classifier dengan voting lembut.
- **Proses**:
  - Mengumpulkan model terbaik dari pencarian grid.
  - Melatih VotingClassifier dengan model-model ini.
  - Mengevaluasi model ensemble menggunakan cross-validation 5-lipat.
  - Menambahkan kinerja model ensemble ke dalam DataFrame.

### 9.3 Penanganan Keseimbangan Kelas
- **Proses**:
  - Menerapkan SMOTE-Tomek untuk menyeimbangkan distribusi kelas dalam data pelatihan.
  - Mencetak jumlah kelas sebelum dan sesudah resampling.

## 10. Pelatihan Model Lanjutan

### 10.1 Pencarian Grid dengan Data yang Telah Disampling
- **Fungsi**: `grid_train_resampled`
- **Tujuan**: Menemukan parameter terbaik untuk model menggunakan data yang telah disampling.
- **Proses**:
  - Melakukan pencarian grid dengan data yang telah disampling.
  - Menyimpan hasil dalam DataFrame.

### 10.2 Model Ensemble dengan Data yang Telah Disampling
- **Fungsi**: `ensemble_train_resampled`
- **Tujuan**: Membangun dan mengevaluasi model ensemble dengan data yang telah disampling.
- **Proses**:
  - Membuat Voting Classifier dari model-model yang telah
  - **Fungsi**: `ensemble_train_resampled`
  - **Tujuan**: Membangun dan mengevaluasi model ensemble dengan data yang telah disampling.
  - **Proses**:
    - Membuat Voting Classifier dari model-model yang telah disampling.
    - Mengevaluasi menggunakan cross-validation 5-lipat.
    - Menyimpan hasil dalam DataFrame.

## 11. Pengurangan Dimensi

### 11.1 Aplikasi PCA pada Data
- **Proses**:
  - Menerapkan PCA untuk mengurangi dimensi data pelatihan.
  - Menyimpan data yang telah ditransformasikan dalam DataFrame baru.

### 11.2 Pencarian Grid dengan Data yang Diproses PCA
- **Fungsi**: `grid_train_PCA`
- **Tujuan**: Menemukan parameter terbaik untuk model menggunakan data yang telah diproses PCA.
- **Proses**:
  - Melakukan pencarian grid dengan data yang telah ditransformasikan PCA.
  - Menyimpan hasil dalam DataFrame.

### 11.3 Model Ensemble dengan Data yang Diproses PCA
- **Fungsi**: `ensemble_train_PCA`
- **Tujuan**: Membangun dan mengevaluasi model ensemble dengan data yang telah diproses PCA.
- **Proses**:
  - Membuat Voting Classifier dari model-model yang telah diproses PCA.
  - Mengevaluasi menggunakan cross-validation 5-lipat.
  - Menyimpan hasil dalam DataFrame.

## 12. Pelatihan Model Akhir

### 12.1 Pencarian Grid dengan Data PCA dan Disampling
- **Fungsi**: `grid_train_PCA_resample`
- **Tujuan**: Menemukan parameter terbaik untuk model menggunakan data yang telah diproses PCA dan disampling.
- **Proses**:
  - Melakukan pencarian grid dengan data yang telah ditransformasikan PCA dan disampling.
  - Menyimpan hasil dalam DataFrame.

### 12.2 Model Ensemble dengan Data PCA dan Disampling
- **Fungsi**: `ensemble_train_PCA_resample`
- **Tujuan**: Membangun dan mengevaluasi model ensemble dengan data yang telah diproses PCA dan disampling.
- **Proses**:
  - Membuat Voting Classifier dari model-model yang telah diproses PCA dan disampling.
  - Mengevaluasi menggunakan cross-validation 5-lipat.
  - Menyimpan hasil dalam DataFrame.

## 13. Evaluasi Model pada Data Uji

- **Proses**:
  - Menggunakan setiap model untuk memprediksi data uji.
  - Mencetak laporan klasifikasi dan F1-score makro.
  - Menyimpan metrik evaluasi dalam DataFrame.

## 14. Analisis Hasil

### 14.1 Pengurutan dan Pembulatan Hasil Evaluasi
- **Proses**:
  - Mengurutkan DataFrame berdasarkan metrik evaluasi.
  - Memperbarui indeks dan membulatkan nilai numerik untuk keterbacaan.

### 14.2 Menampilkan Hasil Model Terbaik
- **Proses**:
  - Menampilkan metrik evaluasi dari model yang berkinerja terbaik setelah pengurutan untuk analisis akhir.

### 14.3 Menyimpan Semua Objek Model
- **Proses**:
  - Menyimpan semua objek model ke dalam file biner dengan nama yang diambil dari `model_DF.model_name` menggunakan format pickle.
 
### 14.3 Analisis Hasil Model Berdasarkan Metrik Penting
- **Macro F1-Score Tertinggi**: Model `BEST_ensemble_models_byVoting_PCA` dan `BEST_xgb_PCAResampled` (0.72).
- **F1-Score Nasabah Deposit**: Model `BEST_ensemble_models_byVoting_PCA` (0.76).
- **F1-Score Nasabah Tidak Deposit**: Model `BEST_xgb_PCA` (0.76).
- **Macro Recall Tertinggi**: Model `BEST_ensemble_models_byVoting_PCA` (0.72).
- **Recall Nasabah Deposit**: Model `BEST_xgb_PCA` (0.82).
- **Recall Nasabah Tidak Deposit**: Model `BEST_xgb` (0.77).
- **Macro Precision Tertinggi**: Model `BEST_ensemble_models_byVoting_PCA` (0.74).
- **Precision Nasabah Deposit**: Model `BEST_xgb` (0.77).
- **Precision Nasabah Tidak Deposit**: Model `BEST_xgb` (0.76).

    Ketidakseimbangan kelas mempengaruhi performa model. Teknik SMOTE-Tomek dan PCA memperbaiki distribusi kelas dan mengurangi dimensi fitur, meningkatkan hasil model.


## 15. Wawasan Data

### 15.1 Analisis Histogram
- **Usia**: Kelompok umur 16-28 dan 50-96 cenderung lebih banyak melakukan deposit.
- **Saldo**: Rentang saldo 3000-12000 menunjukkan kecenderungan yang lebih tinggi untuk melakukan deposit.
- **Jumlah Kontak**: Kontak yang dilakukan hanya sekali menunjukkan kemungkinan lebih tinggi untuk deposit.
- **Hari Sejak Kontak Terakhir**: Rentang 40-240 dan 400-840 hari menunjukkan kecenderungan yang lebih tinggi untuk deposit.

### 15.2 Fitur Kategorikal
- **Pekerjaan**: Pekerjaan seperti retirement, student, unemployed, dan management lebih cenderung untuk melakukan deposit.
- **Status Perumahan & Pinjaman**: Tanpa pinjaman rumah dan tanpa pinjaman cenderung lebih sering melakukan deposit.
- **Bulan**: Bulan Oktober, Maret, April, September, Februari, dan Desember adalah bulan dengan frekuensi deposit yang lebih tinggi.
- **Hasil Kampanye**: Kategori seperti success dan other menunjukkan kecenderungan yang lebih tinggi untuk melakukan deposit.
- **Kontak**: Pelanggan yang dihubungi melalui **`cellular`** juga memiliki kecenderungan yang lebih tinggi untuk melakelakukan deposit.



### Kesimpulan

1. Model **BEST_ensemble_models_byVoting_PCA** menunjukkan performa yang solid dalam mendeteksi nasabah non-deposito, dengan recall mencapai 84.3%. Ini mengindikasikan kemampuan model dalam menangkap sebagian besar nasabah non-deposito dan mengurangi kesalahan False Negatives. Precision-nya juga tinggi pada nasabah deposito, mencapai 77.7%, menandakan akurasi yang baik dalam mengidentifikasi nasabah deposito. Namun, recall untuk nasabah deposito berada pada 59.9%, menunjukkan adanya ruang untuk perbaikan dalam mendeteksi lebih banyak kasus deposito.

2. Model ini dapat **mengurangi biaya akuisisi pelanggan (CAC) hingga 35%**. Hal ini disebabkan oleh kemampuannya dalam **mengidentifikasi nasabah deposito dan non-deposito dengan efisien**, yang berdampak langsung pada **penghematan biaya akuisisi per nasabah deposito hingga USD 58**. Dengan **F1-Score rata-rata 71.9%**, model ini menunjukkan **keseimbangan yang baik antara precision dan recall**, menjadikannya alat yang sangat efektif untuk meningkatkan **efisiensi kampanye pemasaran**.

    Sebagai perbandingan, riwayat sebelumnya menunjukkan bahwa **rasio nasabah deposito terhadap non-deposito sekitar 48/52**, dengan **rate konversi nasabah deposito hanya 48%**. Dengan menggunakan model ini, kita dapat **mengatasi tantangan konversi yang lebih rendah** dan **mengoptimalkan biaya akuisisi** yang sebelumnya rata-rata USD 88 (berasal dari **focus-digital.co**).




### Rekomendasi

Untuk meningkatkan efektivitas kampanye pemasaran deposito, pertimbangkan rekomendasi berikut:

1. **Fokuskan Kampanye Pemasaran:**
   - **Kelompok Umur:** Targetkan kelompok umur 16-28 dan 50-96, yang menunjukkan kecenderungan lebih tinggi untuk melakukan deposit.
   - **Saldo:** Pilih nasabah dengan saldo antara 3000-12000.
   - **Kontak:** Lakukan hanya satu kontak kepada calon nasabah, karena mereka menunjukkan kemungkinan lebih tinggi untuk melakukan deposit.
   - **Hari Sejak Kontak Terakhir:** Prioritaskan nasabah dengan rentang 40-240 dan 400-840 hari sejak kontak terakhir untuk meningkatkan kemungkinan deposit.

2. **Fitur Kategorikal:**
   - **Pekerjaan:** Fokuskan pada individu dengan pekerjaan retirement, student, unemployed, dan management.
   - **Pinjaman:** Targetkan nasabah yang tidak memiliki pinjaman rumah dan pinjaman.
   - **Bulan:** Lakukan pemasaran intensif pada bulan Oktober, Maret, April, September, Februari, dan Desember.
   - **Hasil Kampanye Sebelumnya:** Targetkan nasabah dengan hasil kampanye sebelumnya seperti success dan other.
   - **Metode Kontak:** Utamakan kontak melalui metode cellular, karena metode ini menunjukkan kecenderungan lebih tinggi untuk menghasilkan deposit.

3. **Penyesuaian Data:**
   - Model ini cocok untuk data dengan rentang umur 18-95 tahun, saldo -6847 hingga 66653, jumlah kontak 1 hingga 63, dan hari sejak kontak terakhir -1 hingga 854. Data di luar rentang ini mungkin memerlukan penyesuaian.
   - Data kategorikal harus sesuai dengan nilai-nilai yang telah ditentukan seperti pekerjaan ('admin.', 'self-employed', 'services', 'housemaid', 'technician', 'management', 'student', 'blue-collar', 'entrepreneur', 'retired', 'unemployed'), status perumahan ('no', 'yes'), pinjaman ('no', 'yes'), jenis kontak ('cellular', 'telephone', 'unknown'), bulan ('jun', 'apr', 'may', 'nov', 'jan', 'sep', 'feb', 'mar', 'aug', 'jul', 'oct', 'dec'), hasil pemasaran ('failure', 'other', 'success', 'unknown'), dan status deposito ('yes', 'no').

Jika data nasabah tidak sepenuhnya sesuai dengan kriteria rekomendasi, teknik machine learning dapat digunakan untuk analisis lebih mendalam. Algoritma pembelajaran mesin dapat membantu dalam mengidentifikasi pola yang tidak terdeteksi oleh analisis tradisional, memungkinkan penyesuaian strategi pemasaran yang lebih efektif dan pengambilan keputusan yang lebih terinformasi.
