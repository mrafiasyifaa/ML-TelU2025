# 🎯 ** Chapter 1 - The Machine Learning Landscape**

## *Tantangan dan Strategi dalam Machine Learning*
### 1. Fitur yang Tidak Relevan dan Pentingnya Feature Engineering ###
   - Salah satu tantangan utama ML adalah keberadaan fitur yang tidak relevan dalam data.
   - *Feature Engineering* berperan penting melalui:
     (1) Pemilihan fitur terbaik agar hanya fitur penting yang digunakan
     (2) Ekstraksi fitur untuk menggabungkan fitur yang relevan
     (3) Penciptaan fitur baru dengan menambah data tambahan
   - Tujuannya agar model belajar dari fitur yang benar-benar menunjukkan pola yang mendukung prediksi akurat
---

### 2. Masalah Overfitting dan Underfitting ###
   - *Overfitting* terjadi saat model terlalu kompleks sehingga menangkap *noise* data pelatihan, tetapi gagal pada data baru
   - Solusi dari *Overfitting* adalah dengan menyederhanakan model, kumpulkan data lebih banyak, bersihkan data dari *noise*, atau gunakan **regularisasi** untuk memberi batasan pada ukuran parameter
   - *Underfitting* terjadi ketika model terlalu sederhana untuk menangkap pola data
   - Solusi dari *Underfitting* adalah menggunakan model yang lebih kompleks, perbaiki fitur, atau kurangi batasan yang terlalu ketat
---

### 3. Evaluasi dan Validasi Model ###
   - Evaluasi dilakukan dengan data pengujian terpisah dari data pelatihan untuk mengukur generalisasi model
   - Error tinggi pada data uji namun rendah pada data latih --> Ini adalah indikasi *overfitting*
   - Tuning *hyperparameter* dan pemilihan model yang tepat penting untuk keseimbangan antara akurasi dan generalisasi
   - Data pelatihan harus representatif terhadap kondisi nyata untuk menghindari bias dan prediksi keliru
---

### 4. Asumsi Model dan Teorema "*No Free Lunch*" ###
   - Tidak ada model yang unggul di semua kasus - setiap model memiliki asumsi yang mendasar
   - Penting untuk menguji beberapa model dan membuat asumsi yang rasional sesuai konteks masalah
   - Kualitas data juga sangat berpengaruh - data yang tidak lengkap, kotor, atau salah dapat menurunkan akurasi model
---

### 5. Jenis Sistem dalam Machine Learning ###
   - *Clustering* (*unsupervised learning*): Mmngelompokkan data berdasarkan kemiripan fitur
   - Visualisasi Data: membantu memahami struktur dan pola tersembunyi dalam data
   - *Dimensionality Reduction*: menyederhanakan data dengan menggabungkan fitur yang berkorelasi agar analisis dan visualisasi lebih mudah
---

### 6. *Semi-Supervised* dan *Reinforcement Learning* ###
   - *Semi-Supervised Learning*: memanfaatkan sebagian data berlabel dan tidak berlabel untuk meningkatkan pembelajaran
   - *Reinforcement Learning*: agen belajar melalui interaksi lingkungan, memperoleh *reward* atau *punishment*, dan mengoptimalkan pengambilan keputusan
---

### 7. Pembelajaran *Batch vs Online* ###
   - *Batch Learning*: pelatihan dilakukan *offline* dengan seluruh data sekaligus
   - *Online Learning*: pelatihan dilakukan secara bertahap seiring data masuk, pemantauan performa dilakukan dengan sering agar performa tidak menurun akibat data yang buruk atau berubah
---

### 8. Pembelajaran Berbasis Instansiasi dan Model ###
   - *Instance-based Learning*: prediksi dilakukan dengan membandingkan data baru terhadap contoh yang mirip dari data lama
   - *Model-based Learning*: membangun representasi atau fungsi dari data untuk melakukan prediksi secara general
---

### 9. Faktor Penentu Keberhasilan dalam *Machine Learning* ###
   - Tantangan Utama: kualitas data, kuantitas data, serta kecocokan algoritma
   - Data yang sedikit, tidak representatif, atau berkualitas rendah akan menurunkan performa model
   - Dengan data yang cukup dan berkualitas, perbedaan performa antar algoritma cenderung kecil
   - Oleh karena itu, pengumpulan dan pembersihan data menjadi aspek krusial untuk mencapai hasil yang optimal
---
