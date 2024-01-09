# Machine Learning Segmentation for Targeted Marketing Strategies 
Sebuah perusahaan dapat berkembang dengan pesat saat mengetahui perilaku customer personality nya, sehingga dapat memberikan layanan serta manfaat lebih baik kepada customers yang berpotensi menjadi loyal customers. Dengan mengolah data historical marketing campaign guna menaikkan performa dan menyasar customers yang tepat agar dapat bertransaksi di platform perusahaan, dari insight data tersebut fokus kita adalah membuat sebuah model prediksi kluster sehingga memudahkan perusahaan dalam membuat keputusan

## Latar Belakang
- Memahami perilaku dan kepribadian pelanggan untuk memberikan pelayanan yang lebih baik kepada calon pelanggan setia.
- Mengidentifikasi pelanggan yang tepat untuk meningkatkan efisiensi dalam strategi pemasaran dan mencapai target penjualan yang diinginkan.

## Objective
Membangun sebuah model klaster yang akan memberikan kemudahan bagi perusahaan dalam meningkatkan efektivitas kampanye pemasaran.

## Business Metrics
Recency, Frequency, Monetary (RFM)

## Dataset 
Data yang digunakan dalam analisis tersedia dalam berkas "marketing_campaign_data.csv". Yang terdiri dari 2240 baris, 30 kolom

## Exploratory Data Analysis (EDA)
**Hubungan kolom Income dengan Conversion rate**
![Hubungan kolom Income dengan Conversion rate](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/fa79f438-c79f-485f-9437-ed9c2b342a4b)
  
**Hubungan kolom Income dengan recency**
![Hubungan kolom Income dengan recency](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/6647685f-08bb-48b9-add3-065c9d144737)

**Hubungan kolom Income and frequency**
![Hubungan kolom Income and fequency](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/1c24af0d-7234-4695-8f88-2dfe1683803f)

**Hubungan kolom Income dengan Monetary**
![Hubungan kolom Income dengan Monetary](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/ec57386a-8949-43ea-bc29-785bf82cb6d4)

**Hubungan kolom Usia dengan Conversion Rate**
![Hubungan kolom Usia dengan Conversion Rate](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/236c030c-489a-4f75-ad95-17baa5de4f2b)

**Hubungan kolom Usia dengan recency**
![Hubungan kolom Income dengan recency](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/7a052ccb-1c87-406b-b33e-ad2383a1a973)

**Hubungan kolom Usia dengan frequency**
![Hubungan kolom Usia dengan frequency](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/8b557099-f6a8-4eb0-878a-50f1f4df6b5c)

**Hubungan kolom Usia dengan Monetary**
![Hubungan kolom Usia dengan Monetary](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/5d0fbf60-65ca-4410-8842-86debe61165b)


**Hubungan kolom Usia dengan Income**
![Hubungan kolom Usia dengan Income](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/e2c83f87-14ea-447e-a83d-13fa8738a7ec)

**Interpretasi EDA** <br>
semakin besar income maka conversion rate, frequency dan monetary mengalami peningkatan. sementara untuk fitur recency menyebar secara merata untuk semua kategori income. Sementara itu covesion rate, recency, frequency, dan monetary menyebar secara merata untuk semua kategory usia

## Data Cleaning & Preprocessing
- Feature Engenering dilakuakan untuk mendapatkan kolom kolom baru. kolom baru tersebut diantaranya 'Conversion_Rate', 'Total_Children', 'Total_Purchases', 'Total_Spend', 'Age', 'Total_Campain_Accepted', 'Parents'
- Terdapat kolom yang berisi nilai null yaitu kolom 'Income' dan kolom 'Conversion_Rate'. kolom 'Income' berisi 24 baris data null, hal ini diatasi dengan menggunakan mean. Sedangkan kolom 'Conversion_Rate' yang memiliki 11 bariss data null diatasi dengan menghapus data null tersebut
- Teknik Feature Encoding yang diterapkan adalah Label Encoding pada kolom 'Education' dan kolom 'Marital_Status' , yang memberikan dasar yang kokoh untuk analisis yang lebih mendalam.
- Teknik Feature Scaling yang diterapkan adalah Standarization, yang memberikan dasar yang kokoh untuk analisis yang lebih mendalam.

## Data Modeling
![Fitur yang akan digunakan](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/a4110c2a-2757-475c-b08b-347426d334c9)

Fitur yang akan digunakan dalam modeling adalah 'Recency' yang mewakili recency, 'Total_Purchases' yang mewakili frequency, dan	'Total_Spend' yang mewakili monetary
 
![Elbow Method](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/894dc0b6-1e52-4290-9812-c0c817fd6ca3)
![Clustering](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/70085e6f-eaa5-4421-8b6f-128cb54dd9bf)

Berdasarkan Elbow Method didapatkan hasil 3 jumlah cluster dan model yang dipilih untuk pemodelan adalah Kmeans Clustering

![Silhouette Score](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/983e0f37-f00a-4b0c-8e89-e8c3cc4a497f)

Hasil evaluasi model memperoleh Silhouette Score sebesar 0.50. yang menandakan model ini mampu memisahkan cluster secara optimal
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
**Rata Rata Recency Antar Cluster** <br>
![Rata Rata Recency Antar Cluster](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/2ecb04e0-ae37-4865-b7db-dbd7e97399dd)

**Rata Rata Frequency Antar Cluster** <br>
![Rata Rata Frequency Antar Cluster](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/24466ab8-1955-4f83-9423-21c503542ac1)

**Rata Rata Monetary Antar Cluster** <br>
![Rata Rata Monetary Antar Cluster](https://github.com/GedeWiraWasistha/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/149849772/c250ec66-5581-4f47-bc07-4224afc8ef38)


<br>

## Saran
Saya merekomendasikan untuk memusatkan upaya pemasaran pada **Cluster 1** karena memiliki karakteristik yang sangat menarik. Anggota **Cluster 1** memiliki pendapatan rata-rata yang tinggi, menunjukkan kapasitas finansial yang signifikan untuk melakukan pembelian. Mereka juga menduduki peringkat pertama dalam hal frekuensi pembelian, mencerminkan loyalitas dan aktivitas yang kuat. Nilai moneter mereka sangat tinggi, dan mereka menunjukkan respons yang tinggi terhadap kampanye pemasaran, meskipun jumlah kunjungan situs web mereka lebih rendah. Cluster ini memiliki potensi cross-selling yang signifikan dan aktif menggunakan kupon diskon. Dengan menjaga pelanggan dalam cluster ini dan menarik lebih banyak pelanggan dengan profil serupa, agar perusahaan dapat mencapai pertumbuhan bisnis yang signifikan.




