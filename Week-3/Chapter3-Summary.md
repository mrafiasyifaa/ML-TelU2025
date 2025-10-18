# 🧩 **Chapter 3 - Classification**
---

## 1. Pengenalan ke Klasifikasi dan Dataset MNIST
- ***Supervised Learning*** : Klasifikasi melibatkan prediksi label diskrit (kelas), berbeda dengan regresi yang memprediksi nilai kontinu.
- **Dataset MNIST** : Dataset standar berisi 70.000 gambar angka tulisan tangan. Dataset ini umum digunakan untuk menguji dan membandingkan algoritma klasifikasi.

# 2. Klasifikasi Biner
- **Konsep** : Memecah masalah *multiclass* menjadi masalah biner dengan membedakan satu kelas tertentu dari semua lainnya.
- **Implementasi** : Membuat vektor target seperti *y_target_5 = (y_train == 5)* yang menunjukkan apakah sebuah gambar adalah angka 5.
- **Pilihan Algoritma - SGD Classifier** : Efisien untuk dataset besar. Dapat memperbarui bobot secara inkremental dan mendukung pembelajaran *online*.

# 3. Evaluasi Model dan Metrik Kinerja
- **Keterbatasan Akurasi** : Tidak ideal untuk dataset yang tidak seimbang, di mana satu kelas mendominasi.
- ***Confusion Matrix*** :
  > -Matriks ini menunjukkan prediksi sebenarnya dan yang diprediksi oleh model. <br>
  > -Matriks ini membantu analisis kesalahan secara rinci, termasuk kelas mana yang sering membingungkan. <br>
- **Presisi, Recall, dan F1 Score** :
  > -**Presisi**: Rasio *true positives* terhadap semua prediksi positif. Metriks ini mengukur ketepatan prediksi positif. <br>
  > -**Recall (Sensitivity)**: Rasio *true positives* terhadap jumlah total yang sebenarnya positif. Metriks  ini mengukur tingkat keberhasilan menangkap semua kejadian. <br>
  > -**Skor F1**: Rata-rata harmonis dari presisi dan recall yang memberikan ukuran performa yang seimbang. <br>

# 4. Trade-off Presisi/Recall dan Ambang Keputusan
- ***Trade-off*** : Meningkatkan presisi biasanya menurunkan recall, dan sebaliknya.
-  **Fungsi Keputusan dan Ambang Batas** :
  > -Model menghitung skor untuk setiap *instance*. <br>
  > -Ambang batas digunakan untuk menentukan kelas berdasarkan skor tersebut. <br>
  > -Menyetel ambang batas menyesuaikan keseimbangan antara presisi dan recall untuk hasil optimal. <br>

# 5. Kurva ROC dan AUC
- **Kurva ROC** :
  > -Menggambarkan rasio positif benar (recall) terhadap positif palsu pada berbagai ambang batas. <br>
  > -Memvisualisasikan *trade-off* antara sensitivitas dan spesifikasi. <br>
- ***AUC (Area Under the Curve)*** :
  > -Mengintegrasikan seluruh kurva ROC menjadi satu nilai. <br>
  > -Nilai mendekati 1 menunjukkan model sangat baik dalam membedakan antara kelas. <br>
  > -Pada perbandingan model, AUC yang lebih tinggi menunjukkan model yang lebih baik. <br>

# 6. Strategi Klasifikasi Multiclass
- **Algoritma Multiklas Bawaan** : Beberapa algoritma (seperti *Random Forest* dan *Naive Bayes*) secara alami menangani banyak kelas.
- **Strategi *Binary*** :
  > -*One-vs-the-Rest* (OvR) : Melatih satu *classifier* untuk setiap kelas, yang membedakan antara kelas tersebut dan semua yang lain. Kelas dengan skor tertinggi dipilih. <br>
  > -*One-vs-One* (OvO) : Melatih *classifier* untuk setiap pasangan kelas **(N(N-1)/2)**. Setiap *classifier* memberikan suara, dan kelas yang paling banyak mendapatkan suara menang. <br>
- **Implementasi** : *Scikit-Learn* secara otomatis menangani OvR atau OvO saat menggunakan *classifier* biner untuk masalah multiklas

 # 7. Analisis Kesalahan
 - **Tujuan** : Memahami kesalahan tertentu agar dapat meningkatkan model.
 - **Alat Analisis** :
  > -*Confusion Matrix* : Mengidentifikasi kelas mana yang paling sering membingungkan. <br>
  > -Pemeriksaan Kasus Spesifik : Membantu memahami alasan di balik kesalahan, seperti digit yang buruk penulisannya atau masalah *pre-processing* gambar. <br>

# 8. Klasifikasi Multilabel
- **Konsep** : Memberikan beberapa tabel sekaligus pada satu *instance* (misalnya gambar dapat diberi label 'digit' dan 'berjumlah loop' jika relevan)
- **Implementasi** : Didukung oleh *classifier* seperti *KNeighborsClassifier*
- **Evaluasi** : Metriks seperti skor F1 diperluas untuk pengaturan multilabel guna menilai performa secara menyeluruh
---
