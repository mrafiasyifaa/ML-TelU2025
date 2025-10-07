# 🚀 **Chapter 2 - End-to-End Machine Learning Project**
---

## Grid Search
- *GridSearchCV* digunakan untuk mencari kombinasi nilai *hyperparameter* terbaik dengan *cross validation*
- Contoh adalah *RandomForestRegressor*
- Parameter terbaik dapat diakses melalui *grid_search.best_params_*
- Estimator terbaik dapat diakses melalui *grid_search.best_estimator_*

## Randomized Search
- *RandomizedSearchCV* lebih disukai untuk ruang pencarian *hyperparameter* yang besar karena mengevaluasi sejumlah kombinasi acak
- Pendekatan ini memungkinkan eksplorasi nilai yang lebih beragam untuk setiap *hyperparameter* dan memberi kontrol atas daya komputasi

## Ensemble Method
> Menggabungkan model terbaik (*ensemble*) dapat meningkatkan kinerja, terutama jika model individual membuat kesalahan yang berbeda
>

## Analisis Model Terbaik dan Error Mereka
- Menganalisis model terbaik memberikan wawasan mengenai pentingnya setiap atribut
- Inspeksi kesalahan spesifik yang dibuat oleh sistem membantu memahami pemyebabnya dan cara memperbaikinya, seperti menambahkan fitur tambahan atau membersihkan *outlier*

## Evaluasi Sistem pada *Test Set*
- Model dievaluasi pada set uji setelah penyesuaian untuk memperkirakan kesalahan generalisasi
- Interval **95%** dihitung kesalahan generalisasi menggunakan *scipy.stats.t.interval()*
- Setelah proyek diluncurkan, solusi dipresentasikan, didokumentasikan, dan dibuat presentasi yang jelas dengan visualisasi

## Pengawasan Sistem
- Setelah *deployment*, solusi disiapkan untuk produksi dan model dijalankan di lingkungan produksi
- Model dapat di-*deploy* sebagai *web service* atau di *cloud* menggunakan platform, contohnya Google Cloud AI
- Pemantuan dan pengawasan kinerja sistem dilakukan secara teratur
- Peringatan pemicu saat terjadi penurunan penting karena model cenderung turun kualitasnya seiring waktu

## *Transformer* Kustomm
- *Transformer* kustom dapat dibuat menggunakan metode *fit()*, *transform()*, dan *fit_transform()*
- *TransformerMixin* menyediakan *fit_transofrm* secara gratis dan *BaseEstimator* menyediakan *get_params()* dan *set_params()* untuk penyetelan *hyperparameter* otomatis

## *Feature Scaling*
- *Feature Scaling* penting karena algoritma *Machine Learning* tidak berkinerja baik dengan atribut numerik yang memiliki skala berbeda
- Dua metode umum adalah *min-max scaling* (normalisasi) dan standardisasi
- *Min-max scaling* mengubah skala nilai ke rentang 0 hingga 1
- Standardisasi mengurangi rata-rata dan membagi dengan standar deviasi
