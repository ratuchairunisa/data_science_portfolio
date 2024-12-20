# Analysis of CO2 Emission Conversion into Biogas as Renewable Energy to Increase Indonesia's GDP
![Biogas is a Renewable Energy Gas Resource](https://www.renewables4u.com.au/wp-content/uploads/2023/05/renewable-energy-sources-for-a-sustainable-future-1024x536.jpg)

Proyek ini dibuat sebagai syarat akhir kelulusan track Data Science di Startup Campus dalam program MSIB Batch oleh Kampus Merdeka

Pada proyek ini kami ingin mengeksplorasi hubungan pada beberapa indikator pertumbuhan ekonomi hijau terhadap pertumbuhan nilai PDB di Indonesia dengan menggunakan model machine learning time series forecasting

## Project Overview
-	Memahami faktor-faktor utama yang mendorong naiknya nilai PDB di Indonesia.
-	Membangun model forecasting time series untuk meramalkan nilai atau tren di masa depan berdasarkan data historis.
-	Memberikan saran berdasarkan temuan analisis kepada para stakeholder agar dapat ditindaklanjuti.

## Dataset
- Sumber Data: 
  -	Data Modelling: OECD – GreenGrowth
  -	Data Pendukung untuk dashboard: Kementerian Energi dan Sumber Daya Mineral Republik Indonesia (ESDM atau KESDM), International Energy Agency (IEA), dan Asosiasi Biogas Indonesia (ABgI)
- Periode Data Modelling: Tahun 1990-2023
- Indikator-Indikator yang Digunakan Pada Analisis:
  -	Real GDP per capita
  -	Population density
  -	Production-based CO2 intensity, energy-related CO2 per capita
  -	Total energy supply
  -	Renewable energy supply

## Technologies Used
- Python: Analisis dan pemodelan data.
- Library: pandas, numpy, matplotlib, seaborn, scikit-learn, statsmodels, pmdarima
- Tools: 
    -	Google Colaboratory: Analisis dan pemodelan data
    -	Looker Studio: Dashboard 
    -	Canva: Deck Presentation

## Methodology
### 1.	Data Preparation
- Data Loading. Loading dataset dalam konteks machine learning adalah proses mengimpor atau memasukkan data ke dalam lingkungan pemrograman atau sistem yang digunakan untuk pengembangan model machine learning. Dalam hal ini kita input dataset utama yaitu dari OECD (Organization for Economic Co-operation and Development).
- Data structuring menggunakan pivot table agar lebih rapi.
- Row count check untuk memastikan jumlah data yang digunakan adalah 34 baris.
- Handling missing values, menggunakan metode forward fill (ffill) dan backward fill (bfill).
- Handling data duplicate (jika terdapat data duplicate pada data)
### 2.	Statistics for Data Science & Exploratory Data Analysis (EDA)
- Melakukan Exploratory Data Analysis (EDA). Tujuan utama dari EDA adalah untuk memahami struktur, karakteristik, dan pola dalam data. Pada tahap ini, kami memiliki misi untuk menemukan insight atau informasi yang tersembunyi dalam data, mengidentifikasi anomaly,  serta memahami hubungan antar variabel.
- Melakukan Explanatory Data Analysis (ExDA) yang memiliki tujuan utama untuk mengkomunikasikan temuan atau insight yang sudah didapatkan kepada audiens yang lebih luas, seperti stakeholder.
- Melihat Distribusi data
- Identifikasi hubungan linier dan non-linier
- Analisis korelasi antar variabel
- Menjelaskan kondisi dan perbedaan penggunaan mean, median, dan modus
- Menemukan dan mendeskripsikan statistical five summeries
### 3.	Data Preprocessing
- Data splitting: pembagian dataset disebut data splitting yaitu proses membagi dataset menjadi beberapa subset yang terpisah untuk tujuan pelatihan, validasi, dan pengujian model machine learning. Dalam hal ini kami menggunakan rasio yang paling umum digunakan untuk data splitting yaitu 80:20, di mana 80% data digunakan untuk pelatihan (training) dan 20% sisanya digunakan untuk pengujian (testing). Akan tetapi, dalam kasus ini kami menggunakan rasio 90:10 dengan 90% untuk data latih dengan jumlah data sebanyak 30 data dan 10% untuk data uji dengan jumlah data sebanyak 4 data. Untuk data time series, data harus dibagi berdasarkan waktu. Data yang lebih baru digunakan untuk pengujian, sementara data yang lebih lama digunakan untuk pelatihan.
- Standardisasi/Normalisasi: proses seperti standardisasi (mengubah data agar memiliki mean 0 dan standar deviasi 1) atau normalisasi (mengubah data agar berada dalam rentang tertentu) sebaiknya dilakukan setelah splitting. Ini karena Anda ingin memastikan bahwa test set benar-benar terpisah dari data pelatihan, dan standardisasi atau normalisasi dilakukan hanya berdasarkan data pelatihan.
### 4. Modelling 
Menggunakan algoritma model ARIMA dan ARIMAX untuk time series forecasting.

## Model Results
### 1.	Algoritma Model yang digunakan:
- ARIMA (Autoregressive Integrated Moving Average). ARIMA adalah model peramalan deret waktu klasik yang menangkap pola dan tren non-musiman dalam data. Model ARIMA khususnya digunakan untuk data deret waktu stasioner, di mana rata-rata dan variansnya tetap konstan dari waktu ke waktu.
- Akurasi Model: Model yang dibangun menunjukkan tingkat akurasi yang cukup baik dengan metrik:
  -	MAE (Mean Absolute Error): 356.60
  -	RMSE (Root Mean Squared Error): 402.16
  -	MAPE (Mean Absolute Percentage Error): 2.95%
      
![ARIMA prediction](image/ARIMA.png)

- ARIMAX (Autoregressive Integrated Moving Average with Exogenous Variables). Model ARIMAX, yang merupakan singkatan dari AutoRegressive Integrated Moving Average dengan eXogenous inputs, merupakan versi lanjutan dari model ARIMA (AutoRegressive Integrated Moving Average). Model ARIMAX memperluas kerangka kerja ARIMA dengan mengintegrasikan variabel eksogen, yang merupakan faktor eksternal yang dapat mempengaruhi waktu luang yang sedang dipelajari. Integrasi ini memungkinkan model untuk memanfaatkan informasi tambahan yang dapat meningkatkan akurasi peramalan secara signifikan.
- Akurasi Model: Model yang dibangun menunjukkan tingkat akurasi yang cukup baik dengan metrik:
  -	MAE (Mean Absolute Error): 317.66
  -	RMSE (Root Mean Squared Error): 359.51
  -	MAPE (Mean Absolute Percentage Error): 2.61%

![ARIMAX prediction](image/ARIMAX.png)

Berdasarkan perbandingan tiga metrik, ARIMAX lebih unggul dengan eror lebih rendah dalam semua metrik, menunjukkan bahwa model dengan penerapan factor/ variable eksternal menghasilkan prediksi masa depan yang lebih akurat.

## Dashboard Visualisasi
Kami telah membuat dashboard interaktif menggunakan Looker Studio untuk memvisualisasikan temuan dari proyek ini yang bisa dilihat pada link berikut https://lookerstudio.google.com/reporting/200f721a-478d-44d8-8bd9-ccf638d9d920

## Insights
- Energi terbarukan khususnya biogas berpotensi mengurangi emisi CO2 dan menumbuhkan ekonomi Indonesia yang dapat dilihat dari pertumbuhan nilai PDB.
- Pemanfaatan energi terbarukan khususnya biogas mendukung terjadinya transisi energi bersih, menekan penggunaan bahan bakar fosil, dan mendukung target Net Zero Emissions.

## Policy Recommendations
1.	Investasi Energi Terbarukan: Peningkatan investasi pada sektor energi terbarukan, khususnya biogas, dapat memberikan dampak positif pada PDB.
2.	Peningkatan Infrastruktur: Penyediaan infrastruktur untuk mendukung pengembangan energi terbarukan, terutama di daerah pedesaan.
3.	Mengedukasi masyarakat awam tentang pentingnya transisi ke energi bersih untuk mendukung keberlanjutan ekonomi dan lingkungan

## Challenges & Learnings
1. Challenges: 
- Keterbatasan data historis yang sedikit memengaruhi performa model time series.
- Kompleksitas hubungan antar variabel ekonomi yang membutuhkan analisis mendalam.
2. Learnings: Proyek ini memberikan wawasan mendalam tentang pentingnya pemanfaatan data dalam menemukan solusi dan  mendukung pengambilan keputusan yang berbasis fakta.

## Kontak
- Author: Ratu Chairunisa
- Email: ratuchairunisa2808@gmail.com
- LinkedIn: www.linkedin.com/in/ratuchairunisa
