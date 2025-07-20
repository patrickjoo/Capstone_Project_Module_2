# **AWS SaaS Sales Analysis**

**Tools:** Python & Tableau<br>
**Visualizations:** Python(Matplotlib/Seaborn) & Tableau<br> 
**Dataset:** AWS Saas Sales

**Table of Contents:**

- **Latar Belakang**
- **Rumusan Masalah**
- **Data/Dataset**
- **Data Understanding**
- **Data Analysis**
- **Kesimpulan**
- **Saran**
- **Visualisasi Tableau**

--- 
 
## **Latar Belakang**
Perusahaan yang bergerak dalam model Software as a Service (SaaS) berbasis Business-to-Business (B2B) menghadapi tantangan besar dalam menjaga pertumbuhan penjualan sekaligus memastikan profitabilitas jangka panjang. Dengan beragamnya segmen pelanggan (SMB, Enterprise, Strategic), variasi produk, serta strategi diskon yang digunakan, perusahaan perlu melakukan evaluasi menyeluruh untuk mengetahui faktor-faktor utama yang memengaruhi performa penjualan dan keuntungan.

---

## **Pernyataan Masalah**
Perusahaan SaaS ini ingin mengevaluasi efektivitas strategi penjualannya, terutama terkait pemberian diskon dan kontribusi profit dari berbagai segmen pelanggan, produk, dan wilayah. Saat ini, strategi diskon digunakan untuk mendorong penjualan, namun belum diketahui apakah diskon tersebut benar-benar menguntungkan perusahaan. Selain itu, belum ada pemetaan jelas mengenai karakteristik pelanggan dan produk yang memberikan profit tertinggi.

Seberapa efektif strategi diskon dalam meningkatkan profit, dan bagaimana karakteristik segmen pelanggan, produk, serta wilayah yang paling berkontribusi terhadap profitabilitas perusahaan?

---

## **Data/Dataset**
Untuk menjawab pertanyaan di atas, kita akan menganalisa data peserta yang sudah dikumpulkan oleh perusahaan. Dataset dapat diakses [di sini](https://www.kaggle.com/datasets/nnthanh101/aws-saas-sales).

Dataset AWS SaaS Sales berisi data transaksi dari sebuah perusahaan SaaS fiktif, mencakup detail pelanggan, produk, diskon, jumlah penjualan, dan profit. Melalui analisis data ini, perusahaan dapat memperoleh wawasan penting untuk menyusun strategi pemasaran, promosi, dan segmentasi yang lebih tepat sasaran.

Terdapat 19 kolom di dalam dataset AWS SaaS Sales, yaitu:
- Row ID: A unique identifier for each transaction.
- Order ID: A unique identifier for each order.
- Order Date: The date when the order was placed.
- Date Key: A numerical representation of the order date (YYYYMMDD).
- Contact Name: The name of the person who placed the order.
- Country: The country where the order was placed.
- City: The city where the order was placed.
- Region: The region where the order was placed.
- Subregion: The subregion where the order was placed.
- Customer: The name of the company that placed the order.
- Customer ID: A unique identifier for each customer.
- Industry: The industry the customer belongs to.
- Segment: The customer segment (SMB, Strategic, Enterprise, etc.).
- Product: The product was ordered.
- License: The license key for the product.
- Sales: The total sales amount for the transaction.
- Quantity: The total number of items in the transaction.
- Discount: The discount applied to the transaction.
- Profit: The profit from the transaction.

---

## **Data Understanding**
- Melihat 5 baris teratas dan terbawah dari dataset AWS SaaS Sales
- Melakukan pengecekan struktur dataset dan tipe data
- Melakukan pengecekan statistik deskriptif kolom numerik
- Melakukan pengecekan unique data pada setiap kolom
- Melakukan pengecekan apakah terdapat missing value

---

## **Data Cleaning**
### 1. Mengubah Data Type
Melakukan konversi pada kolom 'Order Date' yang memiliki tipe data 'object' menjadi 'datetime'
#### 2. Drop Column
Menghapus kolom yang tidak relevan seperti 'Row ID', 'License', 'Contact Name'
#### 3. Check Duplicate
Mengecek apakah terdapat duplikasi data
#### 4. Normalisasi Format Data Categorical
Memastikan kolom kategorikal memiliki penulisan yang seragam untuk mencegah kesalahan pengelompokan saat agregasi
#### 5. Meminjau dan menandai Outlier pada kolom numeric
Untuk mengetahui nilai ekstrem pada kolom numeric
#### 6. Feature Engineering
- Order Year & Order Month

Tujuan: Menyimpan tahun dan bulan pemesanan untuk analisis tren waktu
- Profit Margin
  
Tujuan: Mengukur efisiensi keuntungan per penjualan
- Discount Category

Tujuan: Mengelompokkan diskon ke dalam No, Low, Medium, dan High untuk analisis segmentasi
#### 7. Save Cleaned Data
Mengecek kembali data yang sudah dibersihkan dan diexport menjadi file csv dan xlsx yang sudah rapi

---

## **Data Analysis**
#### 1. Efektivitas Strategi Diskon terhadap Profit
Tujuan: Menilai apakah diskon besar meningkatkan atau justru menurunkan profit.
##### 1.a Apakah diskon berefek berbeda untuk segmen tertentu?
Tujuan : Mengetahui apakah pengaruh diskon terhadap profit berbeda tergantung pada karakteristik segmen yang dilayani
##### 1.b Bagaimana pengaruh tingkat diskon terhadap rata-rata profit margin?
Tujuan: Mencari tahu pengaruh tingkat diskon terhadap Rata-rata Profit Margin
##### 1.c Bagaimana pengaruh diskon terhadap profit berubah dari waktu ke waktu?
Tujuan: Menilai apakah efektivitas diskon dalam menghasilkan profit berubah dari waktu ke waktu, dan apakah ada periode tertentu di mana diskon lebih atau kurang efektif

#### 2. Segmen mana yang paling bernilai bagi bisnis dilihat dari profitabilitas dan efisiensi transaksi?
Tujuan: Mengidentifikasi segmen paling menguntungkan dan efisien

#### 3. Produk Mana yang Paling Menguntungkan?
Tujuan: Menentukan produk mana yang menyumbang profit dan margin tertinggi
##### 3.a Seberapa besar kontribusi produk teratas terhadap total profit dan profit margin?
Tujuan: Mengetahui kontribusi produk teratas terhadap total profit dan profit margin
##### 3.b Produk mana yang memiliki profit margin tinggi namun penjualannya masih rendah?
Tujuan: Mengidentifikasi produk yang memiliki profit margin tinggi namun volume penjualannya masih rendah

#### 4. Region mana yang secara konsisten memberikan kontribusi profit tertinggi?
Tujuan: Menemukan Region dengan kontribusi profit paling tinggi dan konsisten
##### 4.a Bagaimana konsistensi profit bulanan dari masing-masing region?
Tujuan: Untuk menganalisis dan memahami stabilitas atau volatilitas profit bulanan dari setiap region

#### 5. Apakah terdapat korelasi antara jumlah produk yang dibeli (Quantity) dengan profit yang dihasilkan?
Tujuan: Menilai apakah pembelian berdasarkan (Quality) berkorelasi dengan profit tinggi
##### 5.a Apakah kelompok Quantity tinggi memang menghasilkan rata-rata profit lebih tinggi dibandingkan kelompok lainnya?
Tujuan: Membandingkan rata-rata profit antar kelompok pembelian untuk melihat apakah transaksi besar memang lebih menguntungkan.
##### 5.b Apakah terdapat produk yang banyak terjual namun memiliki profit margin yang sangat rendah atau bahkan negatif?
Tujuan: Mengidentifikasi produk yang menghasilkan profit rendah meskipun memiliki penjualan tinggi, atau produk yang membutuhkan jumlah pembelian besar namun kontribusi profitnya kecil
##### 5.c Apakah range Quantity besar justru menyumbang profit kecil atau negatif?
Tujuan: Mengidentifikasi apakah Quantity besar = total profit besar


---

## Kesimpulan
### **Efektivitas Strategi Diskon terhadap Profit**

- Diskon meningkatkan volume penjualan namun tidak selalu meningkatkan profit.
- Diskon tinggi (>20%) cenderung menurunkan profit margin, terutama untuk produk dengan margin kecil.
- Diskon paling efektif diberikan kepada pelanggan dari segmen Strategic dan Enterprise karena mereka cenderung melakukan pembelian dalam nilai besar dan berjangka panjang.
- Transaksi dengan diskon 10–15% cenderung memiliki profit positif tertinggi dibanding tanpa diskon atau diskon ekstrem (>30%).

### **Segmen yang Paling Bernilai**

- Enterprise dan Strategic adalah segmen yang paling menguntungkan.
- Segmen ini memiliki rata-rata nilai kontrak dan profit per transaksi yang tinggi.
- Segmen Enterprise dan Strategic cenderung lebih loyal dan memiliki kontrak jangka panjang.
- Sebaliknya, segmen SMB menghasilkan volume transaksi yang besar, tetapi dengan profit margin yang lebih kecil dan cenderung fluktuatif.
- Segmen Strategic memiliki frekuensi pembelian rendah namun nilai transaksi sangat tinggi.
- SMB sering melakukan repeat order dalam jumlah kecil, tapi banyak di antaranya churn sebelum profit maksimal tercapai.

### **Produk yang Paling Menguntungkan**
- Produk Alchemy menempati posisi teratas dalam hal total profit, terlihat dari bar chart kiri atas dan pie chart (26.9% dari total profit 5 besar).
- Site Analytics dan Data Smasher juga memiliki kontribusi besar terhadap total profit secara absolut.
- Saas Connector Pack – Gold memiliki profit margin tertinggi (sekitar 40%), meskipun total penjualannya relatif rendah.
- Produk seperti Support, Alchemy, dan Data Smasher muncul di dua metrik: baik total profit maupun profit margin yang cukup baik → produk efisien dan bernilai tinggi.
- Dari bubble chart (Profit Margin vs Sales), terlihat bahwa:
    - Beberapa produk dengan sales tinggi justru memiliki profit margin rendah.
    - Produk dengan margin tinggi dan volume penjualan moderat cenderung lebih efisien secara keseluruhan.
    - Ada beberapa produk yang bahkan memiliki profit margin negatif, meski volume penjualannya tidak kecil → indikasi kerugian atau pricing yang tidak tepat.

### **Region yang Konsisten Memberikan Profit Tinggi**
- EMEA (Europe, Middle East, Africa) memberikan kontribusi total profit tertinggi secara keseluruhan (~51.5% dari total), mengungguli Amer (~44.5%) dan jauh di atas Apj (~4.0%).
- Profit margin tertinggi juga berasal dari EMEA, menandakan bahwa profitabilitas transaksi di wilayah ini tidak hanya besar secara nominal, tapi juga efisien dibandingkan biaya.
- Amer (Amerika) juga berkontribusi besar dalam total profit, dengan margin yang hampir setara dengan EMEA, meskipun sedikit di bawah.
- APJ (Asia Pacific & Japan) memiliki kontribusi profit yang sangat kecil dan profit margin paling rendah, bahkan beberapa bulan mencatatkan profit negatif (kerugian).
- Dari tren profit bulanan, EMEA menunjukkan performa lebih stabil dan konsisten meningkat dari waktu ke waktu dibandingkan region lain.
- APJ cenderung memiliki profit yang sangat fluktuatif, sering kali negatif, dan tidak menunjukkan tren pertumbuhan yang kuat.

### **Korelasi antara jumlah produk yang dibeli (Quantity) dengan profit yang dihasilkan**
- Hasil uji korelasi Spearman menunjukkan adanya hubungan yang signifikan antara jumlah produk yang dibeli (Quantity) dan profit yang dihasilkan. Namun, korelasinya bersifat lemah, sehingga kenaikan Quantity tidak selalu diikuti oleh kenaikan Profit secara proporsional.
- Profit cenderung lebih tinggi pada transaksi dengan kuantitas rendah hingga sedang (1–6 unit).
- Rentang kuantitas 2–5 unit menghasilkan total profit tertinggi dibandingkan rentang lainnya.
- Rentang kuantitas besar (10–20 unit) justru memberikan total profit terendah.

## Saran
### **Efektivitas Strategi Diskon terhadap Profit**
- Terapkan strategi diskon berbasis segmen dan produk: jangan gunakan diskon rata untuk semua.
- Gunakan analisis profit incremental untuk menilai apakah diskon benar-benar menambah keuntungan.
- Pertimbangkan diskon loyalitas atau bundling untuk meningkatkan profit jangka panjang.
- Implementasikan sistem tiered discount berdasarkan nilai order atau loyalitas pelanggan, bukan blanket discount.
- Hindari pemberian diskon pada produk yang sudah memiliki permintaan tinggi tanpa insentif.

### **Segmen yang Paling Bernilai bagi Bisnis**
- Fokus retensi pada pelanggan Strategic dan Enterprise.
- Optimalkan akuisisi SMB dengan biaya rendah (otomatisasi, digital funnel).
- Gunakan segmentasi berbasis profit untuk kampanye pemasaran dan customer service yang lebih tepat sasaran.
- Buat model prediktif untuk Customer Lifetime Value (CLV) dan gunakan itu sebagai dasar targeting campaign.
- Sesuaikan layanan pelanggan berdasarkan segmen: self-service tools untuk SMB, dedicated support untuk Strategic dan Enterprise.
- Buat program referral atau insentif untuk memperpanjang masa loyal pelanggan SMB yang profitabel.

### **Produk yang Paling Menguntungkan**
- Prioritaskan promosi untuk produk seperti Alchemy, Support, dan Data Smasher, yang memiliki kontribusi profit tinggi sekaligus margin sehat.
- Pertahankan harga dan positioning produk seperti Saas Connector Pack – Gold, karena meskipun tidak populer, marginnya sangat tinggi.
- Kombinasikan produk high-margin seperti Saas Connector Pack – Gold dengan produk yang penjualannya tinggi namun marginnya tipis.

### **Region yang Konsisten Memberikan Profit Tinggi**
- Fokuskan ekspansi dan alokasi sumber daya di wilayah EMEA, yang terbukti memberikan kontribusi profit tertinggi secara konsisten dan efisien.
- Pertahankan dan perkuat strategi di wilayah Amer, karena wilayah ini juga menunjukkan kontribusi tinggi dan pertumbuhan yang cukup stabil.
- Menerapkan pendekatan yang berbeda antar region:
    - Growth strategy pada Region APJ
    - Retention dan profit optimization pada Region EMEA dan Amer

### **Korelasi antara jumlah produk yang dibeli (Quantity) dengan profit yang dihasilkan**
- Fokuskan strategi penjualan pada range kuantitas optimal (2–5 unit) untuk memaksimalkan profit.
- Hindari asumsi bahwa pembelian dalam jumlah besar akan selalu menghasilkan profit tinggi.
- Evaluasi produk dengan volume penjualan tinggi tapi margin rendah atau negatif.
- Rancang promo atau paket penjualan yang mendorong pembelian dalam jumlah sedang (bukan terlalu kecil atau besar).

---

## Visualisasi Tableau
Berikut adalah link untuk mengakses visualisasi saya berdasarkan data yang sudah dibersihkan: 
https://public.tableau.com/app/profile/patrick.jonathan8124/viz/Dashboard_Capstone2_17530239176520/Dashboard1?publish=yes
![preview_dashboard](https://github.com/user-attachments/assets/4f250ec4-423f-4541-8bbf-5ff6db8c35d0)



