# Laporan

# Judul: Diabetes Disease Prediction

Oleh: Jidan Fikri

# Latar Belakang

Diabetes merupakan salah satu jenis penyakit yang sangat banyak diderita oleh manusia di seluruh dunia.  Menurut artikel dari  Kementrian Kesehatan Republik Indonesia, data dari International Diabites Federation (IDF) menunjukan Indonesia merupakan negara dengan peringkat kelima negara dengan jumlah diabetes terbanyak dengan total 19,5 juga penderita di tahun 2021 dan akan diproyeksikan untuk terus meningkat hingga tahun 2045 sebanyak 28,6 juta penderita. 

Selain mematikan, penyakit diabetes ini termasuk salah satu jenis penyakit yang sulit disadari dan dideteksi pada fase - fase awal kemunculannya. Pada artikel yang sama, Direktur Pencegahan dan Pengendalian Penyakit Tidak Menular Kementrian Kesehatan, Dr. Eva Susanti, S. Kp., M. Kes., mengatakan bahwa risiko seseorang untuk terjangkit penyakit ini dipengaruhi oleh beberapa faktor, beberapa diantaranya yaitu riwayat keluarga yang memiliki penyakit diabetes, kebiasaan konsumsi gula pada makanan ataupun minuman, dan kurangnya berolahraga.

Diabetes bukanlah penyakit yang baru, sebagai penyakit yang sudah ada sejak ratusan tahun silam, sudah banyak penelitian yang membahas tentang penyakit ini. Salah satunya yaitu penelitian yang dilakukan oleh Jack W. Smith et all., pada tahun 1988 dengan judul “Using the ADAP Learning Algorithm to Forecast the Onset of Diabetes Mellitus”. Sesuai judul dari penelitian tersebut, algoritma yang dinamakan ADAP algorithm yang digunakan untuk dapat melakukan melakukan diagnosa prediktif apakah seseorang mengidap diabetes atau tidak. Selain algoritma yang dihasilkan, penelitian ini juga menghasilkan dataset yang sampai sekarang masih sangat populer digunakan yaitu Pima Indian Diabetes Dataset yang berisi data kasus pasien di daerah Phoenix, Arizona, Amerika Serikat pada masa tersebut.

Dengan data yang semakin banyak dan teknologi komputasi yang semakin canggih, penyakit ini sudah seharusnya dapat dideteksi sedini mungkin dengan tingkat akurasi yang memungkinkan untuk dapat melakukan penanganan sesegera mungkin dan mengurangi angka kematian akibat penyakit diabetes. 

Referensi riset dan artikel:

 [https://sehatnegeriku.kemkes.go.id/baca/blog/20240110/5344736/saatnya-mengatur-si-manis/#:~:text=Menurut IDF%2C Indonesia menduduki peringkat,merupakan ibu dari segala penyakit](https://sehatnegeriku.kemkes.go.id/baca/blog/20240110/5344736/saatnya-mengatur-si-manis/#:~:text=Menurut%20IDF%2C%20Indonesia%20menduduki%20peringkat,merupakan%20ibu%20dari%20segala%20penyakit).

Smith, J. W., Everhart, J. E., Dickson, W. C., Knowler, W. C., & Johannes, R. S. (1988). Using the ADAP Learning Algorithm to Forecast the Onset of Diabetes Mellitus. *Proceedings of the Annual Symposium on Computer Application in Medical Care*, 261–265.

# Business Understanding

## Problem Statement

1. Apa saja persiapan yang perlu dilakukan pada data sebelum dapat digunakan untuk pelatihan model machine learning?
2. Bagaimana proses evaluasi model machine learning dilakukan sampai pada akhirnya menemukan performa model yang optimal untuk memprediksi seseorang terkena penyakit diabetes?

## Goals

1. Melakukan preparasi data seperti membersihkan data dari bagian yang kosong, pemerataan distribusi, hingga melakukan analisis mendalam terkait korelasi dari setiap variabel independen terhadap variabel dependen atau variabel target (outcome) sehingga dihasilkan model yang relevan dan akurat.
2. Menggunakan 4 jenis nilai kebenaran diantaranya, Truth Positive (TP), Truth Negative (TN), False Positive (FP), dan False Negative (FN) untuk kemudian membandingkan nilai akurasi, precision, recall, dan f1 score dari algoritma model yang digunakan. 

## Solution Statements

Berdasarkan problem statement di atas, maka disimpulkan solusi yang dapat dilakukan untuk mencapai tujuan dari proyek ini, diantaranya yaitu: 

1. Tahapan preparasi data dilakukan dengan menerapkan beberapa metode, diantaranya:
    1. Membagi dataset menjadi data latih dan data testing dengan perbandingan 70:30 atau 70% data latih dan 30% data testing. 
    2. Mengatasi data kosong dengan melakukan imputasi menggunakan median dari variabel target.
    3. Mengatasi distribusi dari data pada tiap variabel yang tidak simetris dengan menggunakan fungsi natural logaritmik ($ln$). 
    4. Melakukan standarisasi data pada dataset menjadi nilai yang berkisar antara 0 hingga 1 untuk memudahkan model machine learning dalam mengolah dan memahami fitur pada dataset yang digunakan.
    5. Mengatasi imbalance antara label 0 (pasien dengan diagnosa tidak mengalami diabetes) dengan label 1(pasien dengan diagnosa mengalami diabetes) dengan melakukan transformasi data latih menggunakan ***Synthetic Minority Oversampling Technique*** (SMOTE).
2. Case pada proyek ini merupakan binary classification dimana output dari model ini nantinya hanya dua, yaitu label 0 (pasien dengan diagnosa tidak mengalami diabetes) dengan label 1(pasien dengan diagnosa mengalami diabetes). Untuk mencari model terbaik, dilakukan perbandingan berdasarkan akurasi yang dihasilkan dari beberapa model tersebut. Untuk case pada proyek ini, ditetapkan restriksi yaitu hanya menggunakan 3 jenis model yang umumnya digunakan pada data dengan jenis binary classification ini, adapun algoritma yang digunakan adalah sebagai berikut:
    1. Logistic Regression
    2. K Neighbors Classification
    3. Random Forest

# Data Understanding

Dataset yang digunakan pada proyek ini adalah data [**Pima Indians Diabetes Database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database/data)** yang diambil dari platform Kaggle. Terdapat 768 baris data yang merupakan hasil perekaman medis diagnosa pasien wanita berumur setidaknya 21 tahun yang berasal dari daerah Phoenix, Arizona, Amerika Serikat. Adapun variabel - variabel yang ada pada dataset ini adalah sebagai berikut:

1. `Pregnancies` = Merupakan kehamilan yang telah dialami oleh pasien
2. `Glucose` = Merupakan nilai konsentrasi glukosa berdasarkan *oral glucose tolerance test* yang dilakukan oleh pasien 
3. `BloodPressure` = Merupakan nilai diastolik tekanan darah pasien
4. `SkinThickness` = Merupakan nilai pengukuran tebal kulit pada trisep dengan melihat kelenturan otot trisep. Biasanya pengukuran ketebalan ini dilakukan untuk memperkirakan persentase lemak yang ada pada tubuh.
5. `Insulin` = Merupakan nilai kadar level insulin dalam tubuh pasien
6. `BMI` = Body Mass Index (BMI) atau indeks masa tubuh merupakan nilai yang dihasilkan berdasarkan rasio antara berat badan dan tinggi badan pasien
7. `DiabetesPedigreeFunction` = Merupakan fungsi yang nilainya berdasarkan riwayat penyakit yang dimiliki oleh realasi/keluarga pasien. Fungsi sintetis ini dibuat oleh [Jack W. Smith](https://pmc.ncbi.nlm.nih.gov/articles/PMC2245318/) dalam riset yang sama dengan terbitnya dataset ini.
8. `Age` = Merupakan umur pasien
9. `Outcome` = Merupakan kolom output dimana terdapat dua jenis output (binary) yaitu antara 0 dan 1.

Berikut ini merupakan deskripsi statistik dari 

| **Pregnancies** | **Glucose** | **BloodPressure** | **SkinThickness** | **Insulin** | **BMI** | **DiabetesPedigreeFunction** | **Age** | **Outcome** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **count** | 768.000000 | 768.000000 | 768.000000 | 768.000000 | 768.000000 | 768.000000 | 768.000000 | 768.000000 |
| **mean** | 3.845052 | 120.894531 | 69.105469 | 20.536458 | 79.799479 | 31.992578 | 0.471876 | 33.240885 |
| **std** | 3.369578 | 31.972618 | 19.355807 | 15.952218 | 115.244002 | 7.884160 | 0.331329 | 11.760232 |
| **min** | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.078000 | 21.000000 |
| **25%** | 1.000000 | 99.000000 | 62.000000 | 0.000000 | 0.000000 | 27.300000 | 0.243750 | 24.000000 |
| **50%** | 3.000000 | 117.000000 | 72.000000 | 23.000000 | 30.500000 | 32.000000 | 0.372500 | 29.000000 |
| **75%** | 6.000000 | 140.250000 | 80.000000 | 32.000000 | 127.250000 | 36.600000 | 0.626250 | 41.000000 |
| **max** | 17.000000 | 199.000000 | 122.000000 | 99.000000 | 846.000000 | 67.100000 | 2.420000 | 81.000000 |

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