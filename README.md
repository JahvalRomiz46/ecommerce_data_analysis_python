# 📊 E-Commerce Sales Performance & Customer Retention Analysis (Olist Store)

> Data Wrangling · EDA · RFM Analysis · Streamlit Dashboard | Project analisis data end-to-end untuk menjawab pertanyaan: **"Produk apa yang paling menguntungkan, dan siapa pelanggan terbaik Olist Store?"**

## 📌 Latar Belakang

Olist Store adalah platform e-commerce asal Brasil yang menghubungkan ribuan merchant dengan jutaan pelanggan. Dataset publik yang tersedia terdiri dari 8 tabel relasional yang mencakup informasi pesanan, produk, pelanggan, hingga ulasan.

Project ini menganalisis performa penjualan dan perilaku pelanggan secara end-to-end: mulai dari pengumpulan dan pembersihan data dari beberapa sumber, eksplorasi data, hingga penyajian hasil dalam sebuah dashboard interaktif berbasis **Streamlit**.

## 🎯 Pertanyaan Bisnis

- Produk apa yang paling banyak dan paling sedikit terjual?
- Kapan terakhir pelanggan melakukan transaksi? (Recency)
- Seberapa sering pelanggan melakukan pembelian? (Frequency)
- Berapa banyak uang yang dihabiskan pelanggan? (Monetary)

## 💡 Key Findings

| Temuan | Detail |
|---|---|
| **Kategori produk terlaris** | Bed, Bath & Table |
| **Kategori produk terlemah** | Security & Services |
| **Pelanggan paling aktif (Recency)** | Pembelian terakhir 0 hari dari tanggal terbaru dataset |
| **Frequency pelanggan** | Seluruh pelanggan tercatat hanya melakukan 1x transaksi |
| **Pelanggan dengan pengeluaran terbesar (Monetary)** | R$ 13.440,00 |
| **Kota dengan pelanggan terbanyak** | São Paulo, Rio de Janeiro, Belo Horizonte |

> 🔑 **Insight utama:** Nilai Frequency yang seragam (1x transaksi per pelanggan) mengindikasikan tingkat retensi pelanggan yang sangat rendah. Ini adalah sinyal penting bagi tim bisnis untuk memprioritaskan strategi loyalitas dan re-engagement pelanggan.

## 🛠️ Tech Stack

| Tahap | Tools | Fungsi |
|---|---|---|
| **Data Wrangling** | Pandas, NumPy | Pembersihan, penggabungan, dan transformasi data dari 8 tabel |
| **Visualisasi** | Matplotlib, Seaborn | Bar chart dan visualisasi RFM di notebook analisis |
| **Dashboard** | Streamlit | Dashboard interaktif dengan filter rentang tanggal |
| **Environment** | Google Colab, VS Code | Notebook analisis dan pengembangan dashboard |

## ⚙️ Alur Analisis

### 1. Data Wrangling

**Gathering:** Mengumpulkan 8 dataset terpisah (customers, orders, order items, products, sellers, geolocation, payments, reviews) dan menggabungkannya menjadi satu DataFrame utama untuk kebutuhan analisis.

**Assessing:** Mengidentifikasi masalah kualitas data pada setiap tabel, antara lain:
- Missing values pada kolom-kolom tanggal di dataset Orders dan kolom deskripsi di dataset Products
- Nama kategori produk masih dalam Bahasa Portugis di dataset Products

**Cleaning:**
- Missing values pada kolom tanggal diisi menggunakan nilai modus per kolom
- Missing values pada kolom numerik produk diisi menggunakan nilai rata-rata (mean)
- Nama kategori produk diterjemahkan dari Bahasa Portugis ke Bahasa Inggris melalui merge dengan tabel translasi
- Seluruh kolom bertipe tanggal dikonversi ke format datetime

### 2. Exploratory Data Analysis (EDA)

- Menganalisis total penjualan per kategori produk untuk mengidentifikasi produk terlaris dan terlemah
- Mengeksplorasi distribusi pelanggan dan penjual berdasarkan kota
- Menghitung parameter RFM per pelanggan sebagai dasar identifikasi pelanggan terbaik:
  - **Recency:** Jumlah hari sejak transaksi terakhir
  - **Frequency:** Total jumlah pesanan unik per pelanggan
  - **Monetary:** Total nilai belanja per pelanggan

### 3. Visualisasi & Dashboard

Hasil analisis disajikan dalam dua bentuk output:
- **Notebook:** Visualisasi statis menggunakan Matplotlib dan Seaborn untuk menjawab setiap pertanyaan bisnis
- **Streamlit Dashboard:** Dashboard interaktif dengan filter rentang tanggal yang menampilkan performa produk dan parameter RFM secara dinamis

## 📁 Struktur Repositori

| File / Folder | Keterangan |
|---|---|
| notebook.ipynb | Notebook utama berisi seluruh proses wrangling, EDA, dan visualisasi |
| dashboard/dashboard.py | Skrip Streamlit untuk menjalankan dashboard interaktif |
| dashboard/all_data.csv | Dataset gabungan hasil cleaning yang digunakan oleh dashboard |
| data/ | Folder penyimpanan seluruh dataset mentah (8 file CSV) |
| requirements.txt | Daftar library Python yang diperlukan |

## 🚀 Cara Menjalankan Dashboard

1. Clone repositori ini dan pastikan seluruh file dalam folder dashboard tersedia.
2. Install semua dependensi yang diperlukan dengan menjalankan perintah: **pip install -r requirements.txt**
3. Masuk ke direktori dashboard.
4. Jalankan dashboard dengan perintah: **streamlit run dashboard.py**
5. Dashboard akan terbuka otomatis di browser pada alamat **localhost:8501**.

**Catatan:** File all_data.csv dan logo Olist harus berada dalam satu folder bersama dashboard.py agar dashboard dapat berjalan dengan benar.

## 📚 Apa yang Saya Pelajari

- Cara menggabungkan beberapa tabel relasional menggunakan berbagai strategi merge untuk membentuk satu dataset analisis yang utuh
- Pentingnya memilih metode imputasi yang tepat sesuai jenis data, apakah modus untuk kategorikal atau mean untuk data kontinu
- Cara mengimplementasikan analisis RFM dari nol dan menginterpretasikan hasilnya untuk kebutuhan bisnis
- Cara membangun dashboard interaktif berbasis Streamlit dengan filter tanggal yang terhubung langsung ke seluruh visualisasi

*Project ini merupakan bagian dari portofolio Data Analyst. Lihat project lainnya di [GitHub Profile](https://github.com/).*
