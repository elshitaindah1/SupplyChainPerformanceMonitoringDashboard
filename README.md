# Supply Chain Performance Dashboard

## Project Overview

Project ini merupakan **Supply Chain Performance Dashboard** yang dikembangkan menggunakan Tableau untuk memonitor dan menganalisis aktivitas supply chain Cacau Prime Foods selama periode 2023–2024.

Analisis mencakup tiga area utama, yaitu **Production Performance, Inventory Monitoring, serta Procurement & Supplier Monitoring**. Dashboard dirancang untuk mengubah data operasional menjadi informasi yang lebih mudah dipahami untuk mendukung monitoring dan pengambilan keputusan berbasis data.

---

## Dataset

Dataset yang digunakan adalah **Cacau Prime Foods Supply Chain (2023–2024)** yang diperoleh dari Kaggle.

Dataset mencakup data yang berkaitan dengan aktivitas supply chain, seperti production, inventory, logistics, purchasing, sales, serta beberapa tabel dimension yang digunakan untuk mendukung analisis.

**Dataset Source:** [Cacau Prime Foods Supply Chain (2023–2024)](https://www.kaggle.com/datasets/marcoslucena/cacau-prime-foods-supply-chain-20232024)

Dataset terdiri dari 7 tabel utama, yaitu:

| Table | Type | Description |
|---|---|---|
| `dim_product` | Dimension | Informasi master produk |
| `dim_supplier` | Dimension | Informasi supplier |
| `dim_facility` | Dimension | Informasi facility |
| `dim_date` | Dimension | Informasi tanggal dan periode |
| `fact_production` | Fact | Data aktivitas produksi |
| `fact_inventory` | Fact | Data persediaan dan pergerakan stock |
| `fact_purchase` | Fact | Data aktivitas pembelian |

### Raw Data Preview

Screenshot berikut menunjukkan contoh data mentah yang digunakan sebagai sumber analisis sebelum dilakukan data preparation dan visualization.

1. Dimension Tables

<div align="center">

<img src="screenshots/raw_data_product.png" width="350"> <img src="screenshots/raw_data_supplier.png" width="350">

<br>

<img src="screenshots/raw_data_facility.png" width="350"> <img src="screenshots/raw_data_date.png" width="350">

</div>

2. Fact Tables

<div align="center">

<img src="screenshots/raw_data_production.png" width="350"> <img src="screenshots/raw_data_inventory.png" width="350">

<br>

<img src="screenshots/raw_data_purchase.png" width="350">

</div>

---

## Tools

* **Tableau** – Data modeling, calculated fields, data visualization, and dashboard development
* **Excel / CSV** – Data inspection and preparation
* **Kaggle** – Dataset source

---

## Business Problem

Aktivitas supply chain menghasilkan data dari berbagai proses seperti production, inventory, purchasing, dan supplier. Apabila data tersebut dianalisis secara terpisah dalam bentuk tabel, proses monitoring performa operasional menjadi kurang efisien dan sulit untuk mengidentifikasi kondisi yang memerlukan perhatian.

Diperlukan sebuah dashboard yang dapat mengintegrasikan berbagai informasi supply chain ke dalam visualisasi yang interaktif sehingga performa production, kondisi inventory, serta aktivitas procurement dan supplier dapat dipantau secara lebih efektif.

---

## Objectives

Project ini bertujuan untuk membangun dashboard Tableau yang dapat:

1. Memonitor performa dan aktivitas produksi.
2. Menganalisis kondisi serta pergerakan inventory.
3. Memonitor aktivitas purchasing dan supplier.
4. Mengidentifikasi pola dan ketidakseimbangan dalam aktivitas supply chain.
5. Menyediakan informasi yang dapat mendukung evaluasi dan pengambilan keputusan operasional.

---

## Data Preparation

Tahapan data preparation dilakukan untuk memastikan data dapat digunakan secara konsisten dalam proses analisis dan visualization.

### 1. Data Inspection

Memahami struktur dataset, field, tipe data, serta informasi yang tersedia pada setiap tabel.

### 2. Data Modeling
Data modeling dilakukan dengan menghubungkan tabel fact dengan tabel dimension berdasarkan key yang sesuai untuk mendukung analisis produksi, inventori, dan procurement.

A. Inventory Data Model

fact_inventory sebagai tabel utama dihubungkan dengan:

* dim_facility → informasi lokasi fasilitas/gudang
* dim_product → informasi produk dan SKU
* dim_date → informasi waktu untuk analisis tren stok

<img src="screenshots/data_model_inventory.PNG" width="350">

B. Production Data Model

fact_production sebagai tabel utama dihubungkan dengan:

* dim_facility → lokasi fasilitas produksi
* dim_product → jenis produk yang diproduksi
* dim_date → analisis volume produksi berdasarkan waktu

<img src="screenshots/data_model_production.PNG" width="350">

C. Purchase Data Model

fact_purchase sebagai tabel utama dihubungkan dengan:

* dim_facility → fasilitas tujuan pembelian
* dim_supplier → informasi supplier
* dim_date → analisis aktivitas pembelian berdasarkan waktu

<img src="screenshots/data_model_purchase.PNG" width="350">

### 3. Data Type Preparation

Menyesuaikan tipe data seperti date, quantity, cost, value, dan category agar dapat digunakan dalam analisis.

### 4. Calculated Fields

Membuat calculated fields untuk menghasilkan KPI dan metrik analisis yang dibutuhkan.

Contoh calculated fields yang digunakan:

* Total Production
<div align="center">
<img src="screenshots/kpi_total_production.png" width="350"> 
</div>
* Production Cost
<div align="center">
<img src="screenshots/kpi_production_cost.png" width="350"> 
</div>
* Production Trend
<div align="center">
<img src="screenshots/kpi_production_trend.png" width="350"> 
</div>

---

## Exploratory Data Analysis

Exploratory Data Analysis dilakukan menggunakan Tableau untuk memahami pola dan kondisi supply chain sebelum visualisasi akhir disusun menjadi dashboard.

### 1. Production Performance Analysis

Menganalisis volume produksi, production cost, production time, dan scrap rate berdasarkan produk, facility, dan periode.

### 2. Inventory Monitoring Analysis

Menganalisis opening stock, closing stock, inbound stock, dan outbound stock untuk melihat perubahan serta pergerakan inventory.


### 3. Procurement Analysis

Menganalisis purchase quantity, purchase value, purchase trend, item, supplier, dan lead time.


### 4. Supplier Performance Analysis

Membandingkan supplier berdasarkan purchase activity, lead time, dan quality untuk melihat perbedaan performa antar supplier.

### 5. Cross-Functional Analysis

Menghubungkan hasil analisis **Procurement → Production → Inventory** untuk memperoleh gambaran supply chain secara lebih menyeluruh.

---

## Tableau Dashboards

Hasil exploratory analysis kemudian dikembangkan menjadi tiga interactive dashboards.

### 1. Production Performance Dashboard

Dashboard digunakan untuk memonitor performa aktivitas produksi.

**KPI:**

* Total Production
* Production Cost
* Production Time
* Avg Scrap Rate

**Visualizations:**

* Production by Product
* Production by Facility
* Production Trend

<div align="center">

<img src="screenshots/dashboard_production.png" width="800"> 

</div>

---

### 2. Inventory Monitoring Dashboard

Dashboard digunakan untuk memonitor kondisi dan pergerakan inventory.

**KPI:**

* Total Closing Stock
* Total Opening Stock
* Total Inbound Stock
* Total Outbound Stock

**Visualizations:**

* Inventory Stock Trend
* Stock Movement
* Inventory by Product
* Inventory by Facility

<div align="center">

<img src="screenshots/dashboard_Inventory.png" width="800"> 

</div>

---

### 3. Procurement & Supplier Monitoring Dashboard

Dashboard digunakan untuk memonitor aktivitas procurement dan mengevaluasi performa supplier.

**KPI:**

* Total Purchase Quantity
* Total Purchase Value
* Average Purchase Value
* Average Lead Time

**Visualizations:**

* Purchase Trend
* Purchase by Supplier
* Purchase by Item
* Supplier Performance
* Supplier Lead Time
* Supplier Quality

<div align="center">

<img src="screenshots/dashboard_procurement.png" width="800"> 

</div>

---

## Key Insights

### 1. Inventory Accumulation

Total inbound stock mencapai **6.577.119 unit**, lebih tinggi dibandingkan outbound stock sebesar **5.264.982 unit**, menghasilkan net stock increase sebesar **1.312.137 unit**.

Closing stock meningkat dari **8.779.896 unit menjadi 10.092.033 unit**, atau sekitar **14,94%** selama periode analisis.

### 2. High Inventory Concentration

Tiga produk utama, yaitu **SKU_002, SKU_011, dan SKU_017**, masing-masing memiliki closing stock sebesar **3.364.011 unit**.

Ketiga SKU tersebut secara keseluruhan menyumbang **100% dari total closing stock sebesar 10.092.033 unit**, menunjukkan tingginya konsentrasi inventory pada beberapa produk utama.

### 3. Uneven Production Distribution

**CD_Recife** mencatat volume produksi sebesar **1.963.802 unit**, sedangkan **Fabrica_Central** sebesar **400.315 unit** dan **CD_Curitiba** sebesar **396.987 unit**.

Volume produksi CD_Recife sekitar **4,9x lebih tinggi** dibandingkan kedua facility tersebut dan menyumbang sekitar **71%** dari total produksi ketiga facility.

### 4. Procurement Value and Supplier Lead Time

Total purchase value mencapai **148.920.388** dengan average lead time sekitar **9,84 hari**.

Kondisi tersebut menunjukkan pentingnya mempertimbangkan purchase value, lead time, dan supplier quality secara bersamaan dalam evaluasi procurement dan supplier.

---

## Business Recommendations

Berdasarkan hasil analisis, beberapa rekomendasi yang dapat dipertimbangkan adalah:

* Melakukan monitoring rutin terhadap perbedaan inbound dan outbound untuk mengendalikan akumulasi inventory.
* Memprioritaskan monitoring terhadap SKU dengan kontribusi inventory terbesar.
* Melakukan evaluasi kapasitas dan aktivitas produksi pada facility dengan volume produksi tinggi.
* Mempertimbangkan lead time dan quality selain purchase value dalam evaluasi supplier.
* Menyesuaikan aktivitas procurement dengan kebutuhan inventory dan pola produksi.
* Menggunakan dashboard sebagai alat monitoring berkala untuk membantu identifikasi perubahan performa supply chain.

---

## Project Result

Project ini menghasilkan **tiga interactive Tableau dashboards** yang mengintegrasikan informasi production, inventory, procurement, dan supplier dalam satu analytical framework.

Dashboard membantu menyediakan:

* Monitoring performa production.
* Monitoring inventory dan stock movement.
* Monitoring aktivitas procurement.
* Evaluasi supplier berdasarkan lead time dan quality.
* Identifikasi inventory accumulation dan concentration.
* Perbandingan performa antar produk dan facility.
* Insight yang dapat digunakan sebagai dasar evaluasi operasional.

Project ini menunjukkan penerapan **data preparation, data modeling, calculated fields, exploratory data analysis, data visualization, dan business analysis menggunakan Tableau** untuk mengubah data supply chain menjadi informasi yang mendukung pengambilan keputusan.
