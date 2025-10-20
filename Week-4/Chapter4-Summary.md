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
