

<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; min-height: 100vh; font-family: Arial, sans-serif;">

<h1>LAPORAN PROYEK PENGEMBANGAN APLIKASI WEB</h1>

<h2>SISTEM PENJUALAN LAPTOP</h2>

<div style="display: flex; justify-content: center; margin: 20px;">
   <img src="https://github.com/user-attachments/assets/caeede39-4853-46c8-80a8-f0a0d01aaa1c" alt="UTDI" style="width: 30%;">
</div>

<h3>Penyusun:</h3>
<ul style="list-style: none; padding: 0;">
    <li><strong>225410006</strong> - RAMA ADITYA</li>
    <li><strong>225410040</strong> - ACHMAD HERMAWAN</li>
</ul>

<h3>PROGRAM STUDI INFORMATIKA</h3>
<p>FAKULTAS TEKNOLOGI INFORMASI</p>
<p>UNIVERSITAS TEKNOLOGI DIGITAL INDONESIA</p>
<p>2024</p>

</div>


## 1. Pendahuluan

### a. Latar Belakang
Kami telah membuat sebuah aplikasi web yang berfungsi sebagai sistem pencatatan penjualan laptop di toko kami. Aplikasi ini hanya dapat diakses oleh administrator toko. Setiap kali ada pelanggan yang membeli laptop, admin akan memasukkan data-data pembeli seperti nama, kontak, dan jenis laptop yang dibeli ke dalam aplikasi. Data-data ini kemudian akan tersimpan secara rapi dalam sebuah database yang telah kami siapkan. Dengan adanya aplikasi ini, kami dapat dengan mudah melacak semua transaksi penjualan laptop dan mendapatkan data yang akurat untuk keperluan analisis bisnis.

### b. Tujuan
Aplikasi web pencatatan penjualan laptop dirancang untuk membantu bisnis dalam mengelola penjualan laptop secara efisien. Dengan aplikasi ini, kita dapat :
 - Otomatiskan proses penjualan: Catat transaksi dengan cepat dan akurat.
 - Dapatkan data yang akurat: Lacak penjualan, stok, dan pelanggan.
 - Buat keputusan yang lebih baik: Analisis data untuk meningkatkan penjualan.
 - Tingkatkan efisiensi: Sederhanakan proses kerja sehari-hari.
Singkatnya, aplikasi ini membantu dalam mengelola bisnis toko laptop dengan lebih baik dan menguntungkan.

### c. Batasan Masalah
Aplikasi ini dirancang untuk mengotomatiskan dan menyederhanakan proses pencatatan penjualan laptop. Fitur-fitur utamanya mencakup manajemen produk, pelanggan, dan transaksi penjualan. Dengan antarmuka yang user-friendly, pengguna dapat dengan mudah melacak stok, membuat laporan penjualan, dan menganalisis data untuk mendukung pengambilan keputusan bisnis. Fokus utama aplikasi ini adalah pada efisiensi operasional dan akurasi data, sehingga pengguna dapat mengelola bisnis laptop mereka dengan lebih efektif. Fitur-fitur tambahan seperti integrasi dengan sistem akuntansi atau e-commerce dapat dipertimbangkan untuk pengembangan di masa mendatang.n.

## 2. Perancangan Sistem

### a. Rancangan Awal
#### 1) Rancangan Database
Struktur tabel dirancang untuk mengelola data customer, products, orders, payments:

**Tabel Customer:**
- id: integer [Primary Key]
- name: varchar
- email: varchar
- phone: varchar
- address: text
- created_at: datetime

**Tabel Products:**
- id: Integer [Primary Key]
- name: varchar
- description: text
- price: decimal
- stock: integer
- created_at: datetime

**Tabel Orders:**
- id: Integer [Primary Key]
- customer_id: integer
- order_date: datetime
- status: varchar

**Tabel Payments:**
- id: Integer [Primary Key]
- order_id: integer
- payment_date: datetime]
- amount: decimal
- payment_method: varchar
- Status: Varchar


![image](https://github.com/user-attachments/assets/7081644e-8955-483f-8781-38e41d5dd649)


#### 2) Data Flow Diagram (DFD) Level 0
![lv0](https://github.com/user-attachments/assets/aad942c1-11ad-40ef-98a6-decb060e7392)



### b. Realisasi
#### 1. Diagram Relasi Antar Tabel dan Struktur Tabel
![image](https://github.com/user-attachments/assets/99831fe7-3470-4803-8d34-9eceadda4969)



#### 2. Data Flow Diagram (DFD) Level 1
![lv0](https://github.com/user-attachments/assets/882187e3-d2bb-41ed-b1c3-c92a1bb17912)




### 3. Teknologi
Untuk memberikan fleksibilitas dan kontrol penuh dalam pengembangan, kami tidak menggunakan framework dalam proyek ini. Pendekatan ini memungkinkan kami menyesuaikan aplikasi secara spesifik dengan kebutuhan bisnis dan menghindari overhead yang tidak perlu.

---

## 3. Implementasi
link kode : https://drive.google.com/drive/folders/18ZNTzkE7QKD4xMbGvWBko4phmvuAckKd?usp=sharing
---

## 4. Tampilan/Output

### Tampilan untuk Admin
#### **Dashboard**
![image](https://github.com/user-attachments/assets/5120f649-cf27-4dad-9abc-2389c27d0576)

#### **Data Penjualan**
![image](https://github.com/user-attachments/assets/1ed2f277-b391-4538-975f-068321fe1064)

#### **Form Edit**
![image](https://github.com/user-attachments/assets/c37f1176-90c5-49a6-aaf2-eb94260a272b)

#### **Form Tambah**
![image](https://github.com/user-attachments/assets/4f5e8bc2-1671-4fb5-9543-ef535a7eed42)

#### **Form Delete**
![image](https://github.com/user-attachments/assets/6108e8e8-d1d5-48e6-8ae1-7c6889ad39b1)


---

## 5. Langkah-Langkah Menjalankan Aplikasi

1. **Mengakses Halaman Aplikasi**: Buka URL melalui browser.
2. **Tampilan Awal**: Halaman `dashboard` sebagai tampilan awal yang terdapat menu data penjualan dan tambah penjualan.
3. **Menu data penjualan**: Halaman tabel database
4. **Menu tambah penjualan**: Halamam form untuk edit, tambah, dan delete data
---

## 6. Kesimpulan dan Saran

### a. Kesimpulan
Proyek pengembangan aplikasi web untuk pencatatan penjualan laptop telah berhasil diselesaikan dengan baik. Aplikasi ini mampu:
   1. Mengotomatiskan proses pencatatan penjualan dengan efisien dan akurat.
   2. Memberikan kemudahan dalam pengelolaan data pelanggan, produk, dan transaksi.
   3. Mempermudah admin toko dalam melacak penjualan, menganalisis data, dan menyusun laporan untuk mendukung pengambilan keputusan bisnis.
   4. Menyediakan antarmuka yang user-friendly sehingga mudah digunakan oleh admin tanpa memerlukan pelatihan khusus.
      
Penggunaan aplikasi ini diharapkan dapat meningkatkan efisiensi operasional toko, akurasi data, dan pengambilan keputusan berbasis data yang lebih baik.

### b. Saran
Untuk pengembangan lebih lanjut, beberapa saran yang dapat dipertimbangkan adalah:
   1. Integrasi dengan Sistem Akuntansi
      Menambahkan fitur integrasi dengan sistem akuntansi akan mempermudah pencatatan keuangan secara keseluruhan, termasuk pendapatan dan pengeluaran toko.
   2. Pengembangan Sistem Notifikasi
      Memberikan notifikasi otomatis kepada admin untuk stok produk yang hampir habis atau pengingat pembayaran pelanggan.
   3. Fitur Laporan yang Lebih Mendetail
      Menambahkan fitur pembuatan laporan yang lebih mendalam, seperti analisis tren penjualan, performa produk, dan data pelanggan untuk mendukung strategi pemasaran.
   4. Keamanan Data
      Meningkatkan sistem keamanan aplikasi, seperti enkripsi data sensitif dan otentikasi dua faktor, untuk melindungi informasi penting dari akses yang tidak sah.
   5. Pengembangan ke Aplikasi Mobile
       Mengembangkan aplikasi versi mobile agar admin dapat mengakses dan mengelola data kapan saja dan di mana saja.
   6. Integrasi dengan Platform E-Commerce
       Menghubungkan aplikasi dengan platform e-commerce seperti marketplace untuk memperluas jangkauan pasar dan meningkatkan penjualan.
      
Dengan implementasi fitur-fitur tambahan ini, aplikasi dapat memberikan nilai tambah yang lebih besar bagi operasional toko dan mendukung pengembangan bisnis di masa depan.

### Link PDF
https://drive.google.com/file/d/1SpuRy6B-3VQ4d_ymxs7Y6vGIivpJp_TJ/view?usp=sharing
