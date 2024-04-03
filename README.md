# RBL-Sains-Data
Prediksi Rating penjualan samsung 
# Domain Proyek 
Harga devise Handphone merupakan salah satu hal yang sangat cepat berubah dengan seiring waktu dan berkembangnya zaman. Kemampuan memprediksi harga ponsel pintar tentunya membantu pembeli sebelum melakukan transaksi jual beli ponsel pintar

Dalam hal jual beli ponsel pintar sangat bergantung kepada spesifikasi seperti, kapasitas RAM, processor, camera, price, dan battrey. Salah satu faktor yang menarik untuk ditelusuri lebih lanjut adalah faktor dari ratings dan harga ponsel pintar. Oleh karena itu, dengan pertimbangan faktor tersebut sangat mempengaruhi harga pada ponsel. Kemudian harga ponsel dapat diestimasi dengan melihat seberapa besar korelasi pengaruh pada faktor-faktor tersebut. 

Dalam membuat model regresi banyak algoritma yang bisa dipilih. Algoritma yang paling umum dan sering digunakan adalah regresi. Dengan menggunakan regresi dan memasukkan faktor-faktor dari spesifikasi ponsel yang ingin didapatkan maka dapat diprediksi harga ponsel. 

# Business Understanding 
Pengembangan model prediksi harga ponsel pintar samsung berpotensi menjadi salah satu alat bantu dalam mengambil keputusan oleh calon pembeli ponsel pintar samsung. Manfaat nyata dari hasil prediksi harga ponsel yang akurat akan membantu pembeli dan penjual dalam membuat kesepakatan. 

# Problem Statements 
- Berdasarkan pengolahan data yang diperoleh, fitur apa saja yang berpengaruh terhadap penentuan harga ponsel pintar
- Bagaimana cara mengolah data set agar didapat model yang sesuai untuk memprediksi harga ponsel pintar samsung.
- Bagaimana cara meningkatkan nilai performa model harpa ponsel?

# Goals 
- Mengekplorasi seluruh fitur yang ada pada dataset dan melihat korelasi harga dari semua fitur untuk menemukan faktor yang berpengaruh dan faktor yang tidak berpengaruh
- Melakukan proses data wragling dan data preparation terhadap dataset yang kemudian akan dibuat model prediksi harga ponsel pintar Samsung
- Melakukan variasi model untuk memperoleh model paling baik dari beberapa model yang paling baik dari model yang lainnya.

# Solution statements 
- Untuk eksplorasi fitur akan dilakukan analisis univariat dan analisis multivariat. Analisis univariate dilakukan untuk mengetahui persebaran dari sebuah data tunggal. Analisis multivariate dilakukan untuk mengetahui korelasi antar fitur. Teknik yang akan dilakukan adalah catplot, pairplot, dan heatmap untuk melihat Correlation Matrix dari semua fitur yang dimiliki.
- Untuk mendapatkan model prediksi digunakan proses Data Wragling yang meliputi Data Gathering, Data Assesing, dan Data Cleaning.
- Untuk menguji performa model dilakukan pengecekan menggunakan metrik evaluasi

# Data Understanding 
Data yang digunakan dalam pembuatan model merupakan data sekunder. Data diambil dari kaggle dengn nama dataset 
URL : 
Berikut merupakan detail dari dataset 
- Dataset berupa CSV
- Dataset terdiri dari 407 dengan 11 buah fitur yang diukur
- Dataset terdiri dari 5 data kategori dan 6 data numerik
- Dataset tidak memiliki missing value

# Variabel-variabel pada dataset adalah sebagai berikut: 
- Name : Nama model ponsel pintar Samsung dengan berbagai variasi
- Rattings: Peringkat dan ulasan pengguna terkait dengan setiap model dan mencerminkan kepuasan pelanggan
- Price : Harga ponsel Samsung, yang menunjukkan berbagai variasi harga
- imgURL: Gambar terkait model, memfasilitasi untuk membandingkan perbandingan visual
- Storage_ram: Detail tentang kapasitas penyimpanan dan konfigurasi RAM untuk setiap perangkat
- Processor: Rincian sistem operasi dan prosesor untuk menilai kinerja dan kemampuan perangkat
- camera: Informasi tentng spesifikasi kamera yang digunakan pada setiap variasi perangkat
- Display: Spesifikasi terkait layar, seperti ukuran, resolusi, dan teknologi dimana akan memberikan informasi kepada pengguna mengenai pengalaman visual
- Battery: Spesifikasi terkait batteray, termasuk kapasitas dan daya tahan 

Untuk memahami data lebih lanjut, dilakukan Analisis Univariat dan Analisis Multivariat, serta Visualisasi Data

Analisis Univariat merupakan analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel. Jenis visualisasi ini umumnya digunakan untuk memberikan gambaran terkait distribusi sebuah variabel dalam suatu dataset. Sedangkan, Analisis Multivariat merupakan jenis analisis data yang terdapat dalam lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data.

Selain melalui analisis, dilakukan juga Visualisasi Data. Memvisualisasikan data memberikan wawasan mendalam tentang perilaku berbagai fitur-fitur yang tersedia dalam dataset. Teknik visualisasi yang digunakan pada pembuatan model proyek ini adalah dengan menggunakan catplot yang digunakan untuk memplot distribusi data pada data kategori, pairplot yang digunakan untuk melakukan hubungan antar fitur dalam dataset, dan heatmap yang menampilkan korelasi antar fitur yang ada dalam dataset dalam bentuk matriks.

Berikut adalah hasil Exploratory Data Analysis (EDA), dimana Gambar 1 merupakan EDA Analisis Univariat dan Gambar 2 merupakan EDA Analisis Multivariat.

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/85ebf9dd-c65a-4eea-9a4f-041e4e058a14)
Gambar 1a. Analisis Univariat (Data Kategori)

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/b690063c-fbde-4e7e-8a23-0a0c82cea553)
Gambar 1b. Analisis Univariate (Data Numerik)

Berdasarkan Gambar 1a, dapat dilihat bahwa distribusi data kategori pada nama memiliki perbandingan yang tidak sama. Lebih jauh, pada Gambar 1b, untuk data numerik memiliki karakteristik, yaitu:
- koordinat longitude rumah mayoritas berada pada -118 derajat dan -122 derajat dan koordinat latitude rumah mayoritas berada pada 34 derajat dan 38 derajat
- median dari umur rumah banyak terdistribusi pada rentang umur 10 - 40, namun nilai terbanyak terdapat pada nilai 50.
- rata-rata terbanyak untuk data total room dan total bedroom yaitu di antara angka 1000-2000 room dan 200-400 bedroom.
- rata-rata terbanyak untuk data population dan households berada di antara angka 500-1000 dan 200-400.
- median income dan median house value terbanyak masing-masing berada di antara angka 3 dan 200000.distribusi median house value miring ke kanan (right-skewed). Hal ini akan berimplikasi pada model.

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/4105ba7f-eb8f-4149-b6c4-8f3b7d6b8c73)
![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/ecfbd442-bca3-40ce-9481-400470cd9f7d)

Dengan mengamati rata-rata 'price' relatif terhadap fitur kategori di atas, diperoleh insight sebagai berikut:

Pada fitur 'display', rata-rata 'price' cenderung bervariasi. Rentangnya berada antara 14000 hingga 25000. Nilai 'price' tertinggi berada pada nilai 'display' yaitu 'HD+AMOLED' dan nilai 'price' terendah berada pada nilai 'display' yaitu 'LCD'. Sehingga, fitur 'display' memiliki pengaruh yang signifikan terhadap rata-rata 'Price'. Kesimpulan akhir, fitur kategori memiliki pengaruh terhadap 'Price'.

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/220dcd8c-cc2e-4f0d-aae2-476ebe6acf2b)
Fungsi pairplot dari library seaborn menunjukkan relasi pasangan dalam dataset. Dari grafik, terlihat plot relasi masing-masing fitur numerik pada dataset. Pada pola sebaran data grafik pairplot sebelumnya, terlihat bahwa 'ram' memiliki korelasi dengan fitur 'price'. Sedangkan kedua fitur lainnya terlihat memiliki korelasi yang lemah karena sebarannya tidak membentuk pola

Koefisien korelasi berkisar antara -1 dan +1. Ia mengukur kekuatan hubungan antara dua variabel serta arahnya (positif atau negatif). Mengenai kekuatan hubungan antar variabel, semakin dekat nilainya ke 1 atau -1, korelasinya semakin kuat. Sedangkan, semakin dekat nilainya ke 0, korelasinya semakin lemah

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/9c9ac052-b76f-4595-919f-f3c49b9b5f22)
Jika diamati, fitur 'ram' memiliki skor korelasi yang cukup besar (0.61) dengan fitur target 'price'. Artinya, fitur 'price' berkorelasi cukup tinggi dengan keempat fitur tersebut. Sementara itu, fitur lainnya memiliki korelasi negatif sehingga, fitur tersebut dapat di-drop.

# Data Preparation 

