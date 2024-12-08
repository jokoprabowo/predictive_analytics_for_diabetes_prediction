# **Laporan Proyek Machine Learning - Joko Prabowo**
## **Domain Proyek**
Diabetes Melitus (DM) adalah salah satu sindrom yang ditandai dengan kelainan pada metabolik yang terganggu  serta pada  kenaikan  konsentrasi  gula  darah  yang  abnormal  yang  disebabkan oleh defisiensi insulin, ataupun sensitivitas insulin yang rendah dari jaringan, maupun keduanya (Fadhillah et al., 2022). Penyakit ini timbul secara perlahan, sehingga seseorang tidak menyadari bahwa adanya berbagai macam perubahan pada dirinya. Perubahan seperti minum lebih banyak, buang air kecil menjadi lebih sering, berat badan terus menurun, dan berlangsung cukup lama, biasanya tidak diperhatikan, hingga baru di ketahui setelah kondisi menurun dan setelah dibawa ke rumah sakit lalu di periksa kadar glukosa darahnya (Riadi,. 2017). Jumlah penderita diabetes melitus di Indonesia tahun 2000 mencapai 8,43 juta jiwa dan diperkirakan mencapai 21,257 juta jiwa pada tahun 2030, Berdasarkan data Departemen Kesehatan (DepKes) angka prevalensi penderita diabetes di Indonesia pada tahun 2008 mencapai 5,7% dari jumlah penduduk Indonesia atau sekitar 12 juta jiwa (Amir et al., 2015). Oleh karenanya Diabetes Melitus merupakan penyakit yang cukup berbahaya dan perlu peninjauan lebih lanjut mengenai probabilitas penyakit ini di lingkungan masyarakat sekitar.

Di dunia teknologi saat ini teknologi telah melekat dalam kehidupan sehari-hari, teknologi telah mempermudah pekerjaan manusia di setiap bidang kehidupan termasuk kesehatan. Teknologi telah membawa banyak perubahan signifikan dalam dunia kesehatan, menciptakan peluang baru untuk meningkatkan kualitas hidup, mempercepat diagnosis, dan memperbaiki pengobatan. Semakin berkembangnya zaman, semakin berkembang pula teknologi untuk mengatasi permasalahan yang semakin mengusik di bidang kesehatan, dan *machine learning* merupakan salah satu teknologi terbaru yang mampu menyelesaikannya. *Machine learning* merupakan cabang dari kecerdasan buatan (*Artificial Intelligence*) dan ilmu komputer yang berfokus pada penggunaan data dan algoritma untuk meniru cara manusia belajar dan secara bertahap dapat meningkatkan akurasinya. Semakin  bagus  algoritma machine  learning yang digunakan maka akan semakin baik pula keputusan yang keluar (Faiza & Andriani., 2022). *Machine learning* telah membantu manusia dalam menyelesaikan berbagai macam masalah dalam bidang kesehatan. Oleh karenanya dalam proyek ini penulis ingin menggunakan *machine learning* untuk membuat program yang mampu mendeteksi probabilitas seseorang terkena diabetes

## **Business Understanding**
### **Problem Statements**
Berdasarkan latar belakang yang telah dipaparkan. Berikut adalah daftar permasalahan yang perlu diselesaikan dalam proyek ini:
<ul>
  <li>Seberapa besar persentase dari responden yang mengalami diabetes?</li>
  <li>Faktor apa saja yang sangat berpengaruh untuk meningkatkan kemungkinan diabetes?</li>
  <li>Model apa yang paling ampuh untuk memprediksi penderita diabetes?</li>
</ul>

### **Goals**
<ul>
  <li>Mengetahui total persentasi dari responden yang mengalami diabetes.</li>
  <li>Mengetahui faktor-faktor yang mempengaruhi seseorang menderita diabetes.</li>
  <li>Menemukan model yang paling ampuh untuk mendeteksi penderita diabetes.</li>
</ul>

### **Solution Statements**
<ul>
  <li>Melakukan analisis terhadap data responden untuk mengetahui persentase penderita diabetes dari seluruh responden yang ada.</li>
  <li>Melakukan analisis serta menerapkan fungsi visualisai untuk mengetahui faktor-faktor yang sangat mempengaruhi seseorang mengidap diabetes.</li>
  <li>Menerapkan model pada data yang ada serta membandingkan hasil prediksi antara setiap model untuk menemukan model terbaik.</li>
</ul>

## **Data Understanding**
Data yang digunakan dalam proyek ini merupakan data yang aslinya diperoleh dari *National Institute of Diabetes and Digestive and Kidney Diseases* yang kemudian dipublikasikan oleh Akshay Dattatray Khare. Data ini diambil dari pasien perempuan berumur minimal 21 tahun yang merupakan keturunan suku Indian Pima. Data ini memiliki lisensi *CC0: Public Domain* dengan *Usability score* 10.00. Dalam dataset ini memiliki beberapa fitur yang tersimpan kedalam beberapa variabel sebagai berikut:

Variabel|Keterangan
----------|----------
Pregnancies|Jumlah kehamilan
Glucose|Kadar glukosa dalam darah
BloodPressure|Tekanan darah
SkinThickness|Ketebalan kulit
Insulin|Kadar insulin dalam tubuh
BMI|Index massa tubuh
DiabetesPedigreeFunction|Presentase diabetes
Age|Umur
Outcome|Nilai akhir (positif = 1) dan (negatif = 0)

## **Exploratory Data Analysis**
### **Deskripsi Variabel**
Berdasarkan detail deskripsi dari data ditemukan bahwa:

#|Column|Non-Null Count|Dtype
---|---|---|---
0|Pregnancies|768 non-null|int64
1|Glucose|768 non-null|int64
2|BloodPressure|768 non-null|int64
3|SkinThickness|768 non-null|int64
4|Insulin|768 non-null|int64
5|BMI|768 non-null|float64
6|DiabetesPedigreeFunction|768 non-null|float64
7|Age|768 non-null|int64
8|Outcome|768 non-null|int64

Dari tabel diatas dapat disimpulkan bahwa:
<ul>
  <li>Terdapat 6 data numerik dengan tipe data int64, yaitu: Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, dan Age,</li>
  <li>Terdapat 2 data numerik dengan tipe data float64, yaitu: BMI, dan DiabetesPedigreeFunction, serta</li>
  <li>Terdapat 1 data kategorik dengan tipe data int64, yaitu: Outcome yang merupakan target fitur dari proyek ini.</li>
</ul>

Kemudian melalui data deskripsi juga ditemukan informasi statistik dari setiap kolom diantaranya:
|	|Pregnancies|Glucose|BloodPressure|SkinThickness|Insulin|BMI|DiabetesPedigreeFunction|Age|Outcome|
 ---|---|---|---|---|---|---|---|---|---
count|768.000000|768.000000|768.000000|768.000000|768.000000|768.000000|768.000000|768.000000|768.000000
mean|3.845052|120.894531|69.105469|20.536458|79.799479|31.992578|0.471876|33.240885|0.348958
std|3.369578|31.972618|19.355807|15.952218|115.244002|7.884160|0.331329|11.760232|0.476951
min|0.000000|0.000000|0.000000|0.000000|0.000000|0.000000|0.078000|21.000000|0.000000
25%|1.000000|99.000000|62.000000|0.000000|0.000000|27.300000|0.243750|24.000000|0.000000
50%|3.000000|117.000000|72.000000|23.000000|30.500000|32.000000|0.372500|29.000000|0.000000
75%|6.000000|140.250000|80.000000|32.000000|127.250000|36.600000|0.626250|41.000000|1.000000
max|17.000000|199.000000|122.000000|99.000000|846.000000|67.100000|2.420000|81.000000|1.000000

Dimana:
<ul>
  <li>count merupakan jumlah sampel,</li>
  <li>mean merupakan nilai rata-rata,</li>
  <li>std merupakan standar deviasi,</li>
  <li>min merupakan nilai minimum,</li>
  <li>25% merupakan kuartil pertama,</li>
  <li>50% merupakan kuartil kedua,</li>
  <li>75% merupakan kuartil ketiga, dan</li>
  <li>max merupakan nilai maximum.</li>
</ul>

### **Menangani missing value dan outliners**
Sebelum data diproses lebih lanjut, data terlebih dahulu akan dibersihkan dari data yang mengandung nilai kosong, data terduplikat, serta data dengan nilai yang menyimpang (outliners). Hal ini dilakukan agar data-data tidak lengkap tersebut tidak menggangu dalam pengimplementasian model nanti.

Setelah melakukan proses pengecekan mengenai data kosong dan terduplikasi, ternyata data-data tersebut tidak ditemukan dalam dataset di proyek ini sehingga proses akan langsung dilanjutkan untuk menangani data dengan nilai menyimpang (Outliners).

<img src="images/boxplot_of_pregnancies.jpg"/>

## **Referensi**
Fadhillah, R. P., Rahma, R., Sepharni, A., Mufidah, R., Sari, B. N., & Pangestu, A. (2022). Klasifikasi Penyakit Diabetes Mellitus Berdasarkan Faktor-Faktor Penyebab Diabetes menggunakan Algoritma C4. 5. JIPI (Jurnal Ilmiah Penelitian dan Pembelajaran Informatika), 7(4), 1265-1270.

Riadi, A. (2017). Penerapan Metode Certainty Factor Untuk Sistem Pakar Diagnosa Penyakit Diabetes Melitus Pada Rsud Bumi Panua Kabupaten Pohuwato. ILKOM Jurnal Ilmiah, 9(3), 309-316.

Amir, S. M., Wungouw, H., & Pangemanan, D. (2015). Kadar glukosa darah sewaktu pada pasien diabetes melitus tipe 2 di Puskesmas Bahu kota Manado. eBiomedik, 3(1).

Faiza, I. M., & Andriani, W. (2022). Tinjauan Pustaka Sistematis: Penerapan Metode Machine Learning untuk Deteksi Bencana Banjir. Jurnal Minfo Polgan, 11(2), 59-63.
