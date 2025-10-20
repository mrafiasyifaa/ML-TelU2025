# 📐**Chapter 4 - Training Models**
---

## 1. Algoritma Regresi Linier
- *Normal Equation* :
Solusi tertutup (*closed-form*) untuk Regresi Linier yang langsung menghitung parameter model. Efisien untuk dataset kecil, tetapi menjadi mahal secara komputasi saat dataset sangat besar karena operasi matriks.
- Varian *Gradient Descent* :
Algoritme iteratif (*Gradient Descent Batch, Stochastic Gradient Descent, Mini-batch Gradient Descent*) mengoptimalkan parameter dengan memperbaruinya secara bertahap berdasarkan gradien dari fungsi *cost*. Kecepatan konvergensinya tergantung pada varian dan hierparameter yang dipilih.

## 2. Regresi Polinomial
- Tujuan :
Untuk memodelkan hubungan non-linier dengan menambahkan fitur pangkat dari fitur asli, sehingga mengubah model linier menjadi non-linier.
- Implementasi :
Mengembangkan fitur yang mencakup pangkat dari fitur asli (misalnya x, x², x³, dan seterusnya) lalu melatih model linier pada himpunan fitur ini.
- Risiko *Overfitting* :
Polinomial derajat tinggi cenderung *overfit*, menangkap *noise* dalam data bukan pola aktual. Regularisasi atau pengurangan derajat polinomial dapat membantu mengurangi risiko ini.

## 3. Kurva Pembelajaran & *Trade-off Bias-Varians*
### Kurva Pembelajaran:
Grafik yang menunjukkan error pelatihan dan validasi versus ukuran dataset pelatihan membantu mendiagnosis model *underfitting* atau *overfitting*

### *Underfitting* (Bias Tinggi)
Kedua error tinggi dan datar sejak awal, menunjukkan model tidak mampu menangkap kompleksitas data.

### *Overfitting* (Varians Tinggi)
Error pelatihan sangat rendah, tetapi error validasi tinggi dengan jarak yang besar, menandakan model terlalu kompleks dan menyesuaikan *noise*

### *Decomposition Bias-Varians*
- *Bias*
Error karena asumsi salah (misalnya menganggap hubungan linier padahal hubungan bersifat kuadratik). Model bias tinggi cenderung *underfit*
- *Varians*
Error karena sensitivitas berlebihan pada data pelatihan, menimbulkan *overfit*. Model dengan banyak derajat kebebasan (contoh polinomial tinggi) biasanya punya varians tinggi. 
- *Trade-off*
- Meningkatkan kompleksitas model mengurangi bias tetapi meningkatkan varians. Tujuannya adalah menemukan titik keseimbangan yang meminimalkan total error.

## 4. Model Linier Regularisasi
### Tujuan :
Untuk mencegah *overfitting* dengan membatasi parameter model, biasanya dengan menambahkan istilah regulasi ke fungsi kerugian.

### Jenis :
- *Ridge Regression* (Regulerisasi L2) :
Menambahkan penalti sebanding dengan kuadrat dari bobot
> $$J(\theta) = \text{MSE} + \alpha \sum_{i=1}^{n} \theta_{i}^{2}$$ <br>
Mengarahkan bobot menjadi kecil dan haluskan model.

- *Lasso Regression* (Regulerisasi L1) :
Menambah penalti sebanding dengan nilai absolut bobot
> $$J(\theta) = \text{MSE} + \alpha \sum_{i=1}^{n} |\theta_{i}|$$ <br>
Mendorong *sparse* model dengan sebagian bobot bernilai nol, melakukan seleksi fitur otomatis.

- *Elastic Net* :
Menggabungkan penalti L1 dan L2, dikontrol oleh rasio *r*, cocok untuk fitur yang berkorelasi tinggi atau data berdimensi sangat tinggi karena kombinasi kelebihan keduanya.

## 5. Early Stopping
- Konsep :
Menghentikan pelatihan secara dini (misalnya saat menggunakan *Gradient Descent*) saat error validasi tidak lagi menurun atau mulai naik, mencegah *overfitting* selama proses pelatihan.
- Penerapan :
Sangat efektif dengan metode *Gradient Descent* stokastik atau *mini-batch*, karena kurva error bisa berfluktuasi.

## 6. Regresi Logistik
- Gambaran Umum :
Digunakan untuk masalah klasifikasi, memperkirakan probabilitas bahwa suatu input termasuk dalam kelas tertentu dengan memodelkan *log-odd* sebagai fungsi linier dari fitur.

- Model :
> $$p(y=1∣x)=σ(xTθ)=1+e−xTθ1​$$ di mana σ adalah fungsi sigmoid. <br>

- Fungsi Kerugian :
Berdasarkan *cross-entropy*, yang secara penalti menghukum estimasi probabilitas yang salah
> $$J(θ)=−m1​i=1∑m​(y(i)logp(i)+(1−y(i))$$ <br>

- Batas Keputusan :
Titik di mana probabilitas prediksi adalah 0.5 (atau ambang lain) yang memisahkan kelas.

## 7. Regresi Softmax
- *General* dari Regresi Logistik
Mengubah klasifikasi biner menjadi multi-kelas dengan memodelkan probabilitas masing-masing kelas menggunakan fungsi *softmax*
> $$p(y=k∣x)=∑j=1K​exTθj​exTθk​​$$ di mana setiap kelas memiliki vektor parameter sendiri θk​. <br>

- Pelatihan
Memaksimalkan *likelihood* (atau meminimalkan *negative log-likelihood*) dengan pendekatan yang mirip regresi logistik, tapi untuk semua kelas sekaligus.

## 8. *Cross Entropy Loss*
- Mengukur jarak antara distribusi nyata dan distribusi yang diprediksi :
> Cross Entropy $$−i∑​yi​logpi​$$ <br>
- Digunakan sebagai fungsi kerugian pada regresi logistik dan *softmax*, secara efektif menilai kepercayaan diri dalam prediksi yang salah.

## 9. Pilihan Hiperparameter & Efek Regulasi
- Hiperparameter regulasi (α, r) mengontrol kekuatan dan tipe regulasi. Pengaturan yang tepat mencegah *overfitting* atau *underfitting*.
- *Elastic Net* cocok ketika fitur berkorelasi tinggi atau jumlah fitur melebihi jumlah sampel karena menggabungkan kelebihan L1 dan L2.

## 10. Ringkasan
- Pilih algoritma dan teknik regulasi sesuai dengan ukuran data, skala fitur, dan kompleksitas model.
- Gunakan kurva pembelajaran untuk mendiagnosis *underfitting* atau *overfitting*.
- Teknik regulasi seperti *Ridge, Lasso,* dan *Elastic Net* membantu meningkatkan generalisasi model.
- *Early stopping* menawarkan regulasi praktis tanpa harus mengubah model.
- Regresi Logistik dan *Softmax* sangat cocok untuk klasifikasi, dengan *cross-entropy* sebagai fungsi kerugian utama.
