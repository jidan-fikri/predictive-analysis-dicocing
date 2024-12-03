# Laporan

# Judul: Diabetes Disease Prediction

[💕💔Listen to Your Heart: A Disease Prediction🔮](https://www.kaggle.com/code/caesarmario/listen-to-your-heart-a-disease-prediction#7.10-%7C-Model-Comparison-%F0%9F%91%80)

Oleh: Jidan Fikri

# Latar Belakang

Diabetes merupakan salah satu jenis penyakit yang sangat banyak diderita oleh manusia di seluruh dunia.  Menurut artikel dari  Kementrian Kesehatan Republik Indonesia, data dari International Diabites Federation (IDF) menunjukan Indonesia merupakan negara dengan peringkat kelima negara dengan jumlah diabetes terbanyak dengan total 19,5 juga penderita di tahun 2021 dan akan diproyeksikan untuk terus meningkat hingga tahun 2045 sebanyak 28,6 juta penderita. 

Selain mematikan, penyakit diabetes ini termasuk salah satu jenis penyakit yang sulit disadari dan dideteksi pada fase - fase awal kemunculannya. Pada artikel yang sama, Direktur Pencegahan dan Pengendalian Penyakit Tidak Menular Kementrian Kesehatan, Dr. Eva Susanti, S. Kp., M. Kes., mengatakan bahwa risiko seseorang untuk terjangkit penyakit ini dipengaruhi oleh beberapa faktor, beberapa diantaranya yaitu riwayat keluarga yang memiliki penyakit diabetes, kebiasaan konsumsi gula pada makanan ataupun minuman, dan kurangnya berolahraga.

Diabetes bukanlah penyakit yang baru, sebagai penyakit yang sudah ada sejak ratusan tahun silam, sudah banyak penelitian yang membahas tentang penyakit ini. Salah satunya yaitu penelitian yang dilakukan oleh Jack W. Smith et all., pada tahun 1988 dengan judul “Using the ADAP Learning Algorithm to Forecast the Onset of Diabetes Mellitus”. Sesuai judul dari penelitian tersebut, algoritma yang dinamakan ADAP algorithm yang digunakan untuk dapat melakukan melakukan diagnosa prediktif apakah seseorang mengidap diabetes atau tidak. Selain algoritma yang dihasilkan, penelitian ini juga menghasilkan dataset yang sampai sekarang masih sangat populer digunakan yaitu Pima Indian Diabetes Dataset yang berisi data kasus pasien di daerah Phoenix, Arizona, Amerika Serikat pada masa tersebut.

Dengan data yang semakin banyak dan teknologi komputasi yang semakin canggih, penyakit ini sudah seharusnya dapat dideteksi sedini mungkin dengan tingkat akurasi yang tinggi untuk dapat melakukan penanganan sesegera mungkin dan mengurangi angka kematian akibat penyakit diabetes. 

Referensi:

 [https://sehatnegeriku.kemkes.go.id/baca/blog/20240110/5344736/saatnya-mengatur-si-manis/#:~:text=Menurut IDF%2C Indonesia menduduki peringkat,merupakan ibu dari segala penyakit](https://sehatnegeriku.kemkes.go.id/baca/blog/20240110/5344736/saatnya-mengatur-si-manis/#:~:text=Menurut%20IDF%2C%20Indonesia%20menduduki%20peringkat,merupakan%20ibu%20dari%20segala%20penyakit).

Smith, J. W., Everhart, J. E., Dickson, W. C., Knowler, W. C., & Johannes, R. S. (1988). Using the ADAP Learning Algorithm to Forecast the Onset of Diabetes Mellitus. *Proceedings of the Annual Symposium on Computer Application in Medical Care*, 261–265.

# Business Understanding

## Problem Statement

1. Apa saja persiapan yang perlu dilakukan pada data sebelum dapat digunakan untuk pelatihan model machine learning?
2. Bagaimana proses evaluasi model machine learning dilakukan sampai pada akhirnya menemukan performa model yang optimal untuk memprediksi seseorang terkena penyakit diabetes?

## Goals

1. Melakukan preparasi data seperti membersihkan data dari bagian yang kosong hingga melakukan analisis mendalam terkait korelasi dari setiap variabel independen terhadap variabel dependen atau variabel target (outcome) sehingga dihasilkan model yang relevan dan akurat.
2. Menentukan model machine learning dengan membandingkan nilai akurasi dan kesalahan dari setiap algoritma yang digunakan sebagai perbandingan. 

## Solution Statements

[ bagian ini menguraikan secara lebih detail tentang cara meraih poin goals tersebut. (1) Mengajukan 2 atau lebih solution statement, misalnya menggunakan 2 atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning. (2) Solusi yang diberikan harus dapat terukur dengan metrik evaluasi ]

# Data Understanding

Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:

**Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:**

- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:

- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

# Data Preparation

Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

# Modeling

Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

# Evaluation

Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:

- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.
- **--Ini adalah bagian akhir laporan---**

*Catatan:*

- *Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!*
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

# Reference

[https://doi.org/10.1016/0002-9149(89)90524-9](https://doi.org/10.1016/0002-9149%2889%2990524-9) (Paper on the dataset)

[https://doi.org/10.24432/C52P4X](https://doi.org/10.24432/C52P4X) (Dataset)