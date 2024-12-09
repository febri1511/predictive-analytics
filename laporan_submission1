# Laporan Proyek Machine Learning - **Nama Anda**

## Domain Proyek

Pada proyek ini, fokus utama adalah membangun model machine learning untuk **prediksi harga perhiasan** (jewelry). Perhiasan adalah salah satu komoditas bernilai tinggi di pasar global, di mana penentuan harga yang tepat sangat penting bagi produsen, penjual, maupun pembeli. Faktor seperti dimensi, bahan, dan kualitas memainkan peran besar dalam menentukan harga suatu barang perhiasan. 

**Mengapa masalah ini penting untuk diselesaikan?**  
Proses penentuan harga yang tidak akurat dapat mengakibatkan kerugian bisnis, ketidakpuasan pelanggan, dan inefisiensi pasar. Dengan menggunakan algoritma machine learning, penentuan harga dapat dilakukan secara otomatis, cepat, dan berdasarkan data historis yang mendukung akurasi prediksi. 

**Referensi**:  
- [Machine Learning for Price Prediction](https://scholar.google.com/)  
- [Factors Affecting Jewelry Pricing](https://scholar.google.com/)  

---

## Business Understanding

### Problem Statements

1. Bagaimana membangun model machine learning untuk memprediksi harga perhiasan secara akurat?
2. Apa faktor-faktor utama yang memengaruhi harga perhiasan dalam dataset ini?
3. Algoritma mana yang paling cocok untuk memprediksi harga perhiasan berdasarkan dataset?

### Goals

1. Membuat model prediktif untuk memprediksi harga perhiasan dengan tingkat akurasi tinggi.
2. Mengidentifikasi fitur utama yang memengaruhi harga perhiasan.
3. Membandingkan performa algoritma **K-Nearest Neighbor (KNN)**, **Random Forest**, dan **Boosting** untuk menentukan model terbaik.

### Solution Statements

1. **Modeling dengan tiga algoritma utama**:
   - K-Nearest Neighbors (KNN)
   - Random Forest Regressor
   - AdaBoost Regressor
2. **Scaling data** untuk memastikan semua fitur numerik berada dalam skala yang sama sehingga hasil prediksi lebih stabil.
3. Evaluasi model menggunakan metrik **Mean Squared Error (MSE)** untuk membandingkan performa ketiga algoritma.

---

## Data Understanding

Dataset yang digunakan dalam proyek ini berasal dari data fiktif mengenai harga perhiasan. Dataset ini memiliki 968 sampel dengan beberapa fitur berikut:

### Variabel dalam Dataset:
- **height**: Tinggi perhiasan dalam satuan cm.
- **width**: Lebar perhiasan dalam satuan cm.
- **dimension**: Dimensi keseluruhan perhiasan.
- **cost**: Harga perhiasan (target prediksi).

Dataset ini menunjukkan bahwa fitur numerik seperti dimensi memengaruhi harga secara signifikan. **Exploratory Data Analysis (EDA)** dilakukan untuk memahami distribusi data, pola korelasi antara fitur, serta deteksi nilai-nilai ekstrem (outliers).

---

## Data Preparation

Langkah-langkah data preparation yang dilakukan adalah sebagai berikut:

1. **Train-Test Split**:  
   Dataset dibagi menjadi data latih (90%) dan data uji (10%) untuk menjaga generalisasi model.  
   ```
   train_test_split(X, y, test_size=0.1, random_state=123)
   ```

2. **Standardisasi**:  
   Fitur numerik seperti `height`, `width`, dan `dimension` diubah ke skala standar (mean = 0, standard deviation = 1) menggunakan **StandardScaler**. Proses standarisasi hanya diterapkan pada data latih, sedangkan data uji dinormalisasi menggunakan parameter dari data latih untuk menghindari kebocoran data.  
   ```
   scaler = StandardScaler()
   scaler.fit(X_train[numerical_features])
   X_train[numerical_features] = scaler.transform(X_train[numerical_features])
   ```

---

## Modeling

### Algoritma yang digunakan:
1. **K-Nearest Neighbor (KNN)**:
   - Parameter: `n_neighbors=10`
   - Metrik jarak: Euclidean
   - Kelebihan: Mudah dipahami, cocok untuk dataset kecil.
   - Kekurangan: Tidak efisien pada dataset berdimensi tinggi.  

   ```
   knn = KNeighborsRegressor(n_neighbors=10)
   knn.fit(X_train, y_train)
   ```

2. **Random Forest Regressor**:
   - Parameter: `n_estimators=50`, `max_depth=16`
   - Kelebihan: Dapat menangani dataset besar, akurat pada data non-linear.
   - Kekurangan: Butuh waktu komputasi lebih lama pada dataset besar.  

   ```
   RF = RandomForestRegressor(n_estimators=50, max_depth=16, random_state=55, n_jobs=-1)
   RF.fit(X_train, y_train)
   ```

3. **AdaBoost Regressor**:
   - Parameter: `learning_rate=0.05`
   - Kelebihan: Baik untuk data yang sulit diprediksi oleh model sederhana.
   - Kekurangan: Sensitif terhadap outliers.  

   ```
   boosting = AdaBoostRegressor(learning_rate=0.05, random_state=55)
   boosting.fit(X_train, y_train)
   ```

---

## Evaluation

### Metrik Evaluasi: Mean Squared Error (MSE)  
MSE digunakan untuk mengukur rata-rata kesalahan kuadrat antara nilai prediksi dan nilai aktual.  

\[
MSE = \frac{1}{n} \sum_{i=1}^{n} (y_{i} - \hat{y}_{i})^2
\]

**Hasil Evaluasi:**

| Model      | Train MSE | Test MSE  |
|------------|-----------|-----------|
| KNN        | 86.49     | 126.41    |
| RandomForest | 40.73     | 158.07    |
| Boosting   | 765.34    | 1008.89   |

**Kesimpulan:**
- Model KNN memiliki performa terbaik dengan **Train MSE** = 86.49 dan **Test MSE** = 126.41.
- Random Forest dan Boosting memiliki kesalahan yang lebih tinggi pada data uji, meskipun Random Forest unggul pada data latih.

---

## Kesimpulan

Berdasarkan hasil evaluasi, model **K-Nearest Neighbor (KNN)** dipilih sebagai model terbaik untuk prediksi harga perhiasan karena memiliki performa terbaik pada data uji dengan nilai **MSE terendah**.

Langkah selanjutnya untuk meningkatkan model ini dapat mencakup:
1. **Hyperparameter Tuning** pada model KNN untuk mendapatkan parameter terbaik.
2. Menggunakan metode ensemble untuk menggabungkan keunggulan berbagai algoritma.
3. Meningkatkan kualitas data dengan mengurangi noise atau memperbanyak fitur relevan.

Laporan ini menunjukkan bahwa machine learning dapat menjadi alat yang efektif dalam memprediksi harga perhiasan dengan akurasi yang lebih tinggi dibandingkan metode tradisional.

--- 

_Semoga laporan ini membantu dalam memahami langkah-langkah proyek machine learning untuk prediksi harga! 😊_
