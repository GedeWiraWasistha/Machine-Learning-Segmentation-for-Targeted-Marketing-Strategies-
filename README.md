# Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning
Sebuah perusahaan dapat berkembang dengan pesat saat mengetahui perilaku customer personality nya, sehingga dapat memberikan layanan serta manfaat lebih baik kepada customers yang berpotensi menjadi loyal customers. Dengan mengolah data historical marketing campaign guna menaikkan performa dan menyasar customers yang tepat agar dapat bertransaksi di platform perusahaan, dari insight data tersebut fokus kita adalah membuat sebuah model prediksi kluster sehingga memudahkan perusahaan dalam membuat keputusan

## Exploratory Data Analysis
- Hubungan kolom Income dengan Conversion rate
<gambar>
  
- Hubungan kolom Income dengan recency
<gambar>

- Hubungan kolom Income and fequency
<gambar>

- Hubungan kolom Income dengan Monetary
<gambar>

- Hubungan kolom Usia dengan Conversion Rate
<gambar>

- Hubungan kolom Usia dengan recency
<gambar>

- Hubungan kolom Usia dengan frequency
<gambar>

- Hubungan kolom Usia dengan Monetary
<gambar>

- Hubungan kolom Usia dengan Income
<gambar>


**Interpretasi EDA** <br>
semakin besar income maka conversion rate, frequency dan monetary mengalami peningkatan. sementara untuk fitur recency menyebar secara merata untuk semua kategori income. Sementara itu covesion rate, recency, frequency, dan monetary menyebar secara merata untuk semua kategory usia

## Data Cleaning & Preprocessing
- Feature Engenering dilakuakan untuk mendapatkan kolom kolom baru. kolom baru tersebut diantaranya 'Conversion_Rate', 'Total_Children', 'Total_Purchases', 'Total_Spend', 'Age', 'Total_Campain_Accepted', 'Parents'
- Terdapat kolom yang berisi nilai null yaitu kolom 'Income' dan kolom 'Conversion_Rate'. kolom 'Income' berisi 24 baris data null, hal ini diatasi dengan menggunakan mean. Sedangkan kolom 'Conversion_Rate' yang memiliki 11 bariss data null diatasi dengan menghapus data null tersebut
- Teknik Feature Encoding yang diterapkan adalah Label Encoding pada kolom 'Education' dan kolom 'mapping_marital_status' , yang memberikan dasar yang kokoh untuk analisis yang lebih mendalam.
- Teknik Feature Scaling yang diterapkan adalah Standarization, yang memberikan dasar yang kokoh untuk analisis yang lebih mendalam.

## Data Modeling
- Fitur yang akan digunakan dalam modeling adalah 'Recency' yang mewakili recency, 'Total_Purchases' yang mewakili frequency, dan	'Total_Spend' yang mewakili monetary
  <gambar>

- Berdasarkan Elbow Method didapatkan hasil 3 jumlah cluster
<gambar>


- Model yang dipilih untuk pemodelan adalah Kmeans Clustering
<gambar>


- Hasil evaluasi model memperoleh Silhouette Score sebesar 0.50. yang menandakan model ini mampu memisahkan cluster secara optimal
<gambar>


## Customer personality analysis for marketing retargeting
berdasarkan hasil clustering, didapatkan 3 cluster dengan karakteristik : <br>
<br>
**Cluster 0**, yang merupakan cluster terbesar di antara semua cluster yang ada, terdiri dari sebanyak 911 pelanggan. <br>
Berikut adalah beberapa informasi kunci yang menggambarkan cluster ini dengan lebih rinci:
- **Pendapatan Rata-rata**: Anggota dari Cluster 0 memiliki rata-rata pendapatan sekitar 39.563.690. angka ini menempatkan cluster ini dalam urutan kedua terbesar dalam hal income
- **Recency** : Cluster ini memiliki waktu recency tersingkat, yaitu sebesar 23.791541.
- **Frequensi Pembelian**: Frequensi pembelian pada cluster ini relatif rendah, seperti yang terlihat dari rata-rata Total_Purchases yang hanya sekitar 9.429003.
- **Nilai Moneter**: Cluster ini memiliki nilai moneter paling rendah dibandingkan dengan cluster lainnya, yang dapat dilihat dari rata-rata Total_Spend hanya sebesar 164.365,6.
- **Aktivitas Online**: Meskipun memiliki jumlah kunjungan ke situs web tertinggi (NumWebVisitsMonth), cluster ini menempati urutan kedua dalam merespon campaign marketing.
- **Produk Dominan**: Barang-barang yang paling diminati oleh anggota cluster ini adalah MntCoke, MntMeatProducts, MntFishProducts, dan MntGoldProds.
- **Penggunaan Kupon Diskon**: Penggunaan kupon diskon pada cluster ini paling rendah di antara semua cluster lainnya, yaitu sebesar 2.157100.
- **Pilihan Belanja**: Cluster ini cenderung memilih antara belanja online atau kunjungan langsung ke toko fisik.
- **Profil Demografis**: Mayoritas anggota cluster ini adalah orang tua yang sudah memiliki anak.

**Cluster 1**, yang merupakan cluster terbesar kedua di antara semua cluster yang ada, terdiri dari 662 pelanggan. <br>
Berikut adalah informasi terperinci tentang Cluster 1:
-	**Pendapatan Rata-rata**: Anggota Cluster 1 memiliki pendapatan rata-rata sekitar 69.617.530. Ini menjadikan cluster ini sebagai cluster dengan pendapatan tertinggi di antara semua cluster.
-	**Recency**: Cluster ini memiliki waktu recency tersingkat kedua, yaitu sebesar 49.151482.
-	**Frequensi Pembelian**: Cluster ini menduduki peringkat pertama dalam hal frequensi pembelian, dengan Total_Purchases sebesar 22.150384.
-	**Nilai Moneter**: Cluster ini memiliki nilai moneter tertinggi dibandingkan dengan cluster lainnya, yang dapat dilihat dari rata-rata Total_Spend sebesar 1.200.971.
-	**Aktivitas Online**: Meskipun memiliki jumlah kunjungan ke situs web terendah (NumWebVisitsMonth), cluster ini menduduki peringkat pertama dalam hal merespon campaign marketing.
-	**Produk Dominan**: Anggota cluster ini memiliki nilai transaksi yang signifikan untuk semua lini produk.
-	**Penggunaan Kupon Diskon**: Penggunaan kupon diskon pada cluster ini paling tinggi di antara semua cluster lainnya, yaitu sebesar 2.491767.
-	**Pilihan Belanja**: Cluster ini cenderung memilih antara belanja online, katalog, dan kunjungan langsung ke toko fisik.
-	**Profil Demografis**: Sebagian anggota cluster ini bukanlah orang tua.

**Cluster 2**, yang merupakan cluster terkecil di antara semua cluster yang ada, terdiri dari 629 pelanggan.Berikut adalah informasi terperinci tentang Cluster 2: <br>
- **Pendapatan Rata-rata**: Anggota Cluster 2 memiliki pendapatan rata-rata sekitar 38.998.650. Ini menjadikan cluster ini sebagai cluster dengan pendapatan terendah di antara semua cluster.
-	**Recency**: Cluster ini memiliki waktu recency terlama, yaitu sebesar 75.593005.
-	**Frequensi Pembelia**n: Cluster ini menduduki peringkat kedua dalam hal frequensi pembelian, dengan Total_Purchases sebesar 9.793323.
-	**Nilai Moneter**: Cluster ini memiliki nilai moneter tertinggi kedua dibandingkan dengan cluster lainnya, yang dapat dilihat dari rata-rata Total_Spend sebesar 182.810,8.
-	**Aktivitas Online**: Meskipun memiliki jumlah kunjungan ke situs web (NumWebVisitsMonth) tertinggi kedua, cluster ini jarang merespon campaign marketing.
-	**Produk Dominan**: Anggota cluster ini memiliki nilai transaksi yang signifikan pada MntCoke, MntMeatProducts, MntFishProducts, dan MntGoldProds.
-	**Penggunaan Kupon Diskon**: Penggunaan kupon diskon pada cluster ini menempati urutan kedua di antara semua cluster lainnya, yaitu sebesar 2.298887.
-	**Pilihan Belanja**: Cluster ini cenderung memilih antara belanja online dan kunjungan langsung ke toko fisik.
-	**Profil Demografis**: Mayoritas anggota cluster ini adalah orang tua yang sudah memiliki anak.

## Menghitung potential impact dari hasil marketing retargeting dari cluster yang ada
- Rata Rata Recency Antar Cluster
  <gambar>
- Rata Rata Frequency Antar Cluster
  <gambar>
- Rata Rata Monetary Antar Cluster
  <gambar>

<br>

## Saran
Saya merekomendasikan untuk memusatkan upaya pemasaran pada **Cluster 1** karena memiliki karakteristik yang sangat menarik. Anggota **Cluster 1** memiliki pendapatan rata-rata yang tinggi, menunjukkan kapasitas finansial yang signifikan untuk melakukan pembelian. Mereka juga menduduki peringkat pertama dalam hal frekuensi pembelian, mencerminkan loyalitas dan aktivitas yang kuat. Nilai moneter mereka sangat tinggi, dan mereka menunjukkan respons yang tinggi terhadap kampanye pemasaran, meskipun jumlah kunjungan situs web mereka lebih rendah. Cluster ini memiliki potensi cross-selling yang signifikan dan aktif menggunakan kupon diskon. Dengan menjaga pelanggan dalam cluster ini dan menarik lebih banyak pelanggan dengan profil serupa, agar perusahaan dapat mencapai pertumbuhan bisnis yang signifikan.





