

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
Struktur tabel dirancang untuk mengelola data siswa, guru, rombel, dan pengguna:

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

### a. Model
https://github.com/FebiMaharani/Proyek-Pengembangan-APK-Web/blob/main/Projek%20Akhir/model

### b. View
https://github.com/FebiMaharani/Proyek-Pengembangan-APK-Web/blob/main/Projek%20Akhir/view

### c. Controller
https://github.com/FebiMaharani/Proyek-Pengembangan-APK-Web/blob/main/Projek%20Akhir/controller

---

## 4. Tampilan/Output

### 1) Tampilan untuk Guest/Tamu
- **Home**
  <div style="display: flex; flex-wrap: wrap; gap: 10px;">
      <img src ="https://github.com/user-attachments/assets/f6f55bb9-c52e-43b5-b019-6672740c3065" alt="DFD" style="width: 50%;" )
   </div>

- **Profile**
   <div style="display: flex; flex-wrap: wrap; gap: 10px;">
       <img src ="https://github.com/user-attachments/assets/36a80f61-1d31-4bbe-9f4d-5c3765726f4e" alt="Profile" style="width: 50%;" )
   </div>
   
- **Login**
   <div style="display: flex; flex-wrap: wrap; gap: 10px;">
         <img src ="https://github.com/user-attachments/assets/cbacc7c8-725a-4149-962c-c857a222ac71" alt="Login" style="width: 50%;" )
   </div>

### 2) Tampilan untuk Admin
#### **Siswa**: Tampil, Tambah, Edit, Hapus.
<div style="display: flex; flex-wrap: wrap; gap: 10px;">
  <img src="https://github.com/user-attachments/assets/880bb127-9f97-4c12-bebf-fa9537be553d" alt="Siswa Tampil" style="width: 24%;">
  <img src="https://github.com/user-attachments/assets/fe239be4-4a98-4874-8cee-84b04cca6334" alt="Siswa Tambah" style="width: 24%;">
  <img src="https://github.com/user-attachments/assets/512521d1-0ec1-4a21-92a1-6405644bc401" alt="Siswa Edit" style="width: 24%;">
  <img src="https://github.com/user-attachments/assets/de724c57-970c-4cb3-9e41-f98310e7bd02" alt="Siswa Hapus" style="width: 24%;">
</div>

#### **Guru**: Tampil, Tambah, Edit, Hapus.
<div style="display: flex; flex-wrap: wrap; gap: 10px;">
  <img src="https://github.com/user-attachments/assets/fbff3055-236f-4bd2-a247-5218fda18f4a" alt="Guru Tampil" style="width: 24%;">
  <img src="https://github.com/user-attachments/assets/281a1d60-1fea-4335-87ec-98ba7c15770c" alt="Guru Tambah" style="width: 24%;">
  <img src="https://github.com/user-attachments/assets/eafe9625-580a-4ed0-95ba-b46122ac9334" alt="Guru Edit" style="width: 24%;">
  <img src="https://github.com/user-attachments/assets/f1a31d2a-c1e0-4457-aace-1609a1d7883f" alt="Guru Hapus" style="width: 24%;">
</div>

#### **Rombel**: Tampil, Edit, Hapus.
<div style="display: flex; flex-wrap: wrap; gap: 10px;">
  <img src="https://github.com/user-attachments/assets/8d6b488c-f6a7-4c98-9cc5-971407728e57" alt="Rombel Tampil" style="width: 24%;">
  <img src="https://github.com/user-attachments/assets/957db759-7a15-465b-9d35-be6c0e3939ad" alt="Rombel Tambah" style="width: 24%;">
   <img src="https://github.com/user-attachments/assets/a907811d-6a31-4e6d-aca3-3ff3a50aa2a3" alt="Rombel Edit" style="width: 24%;"/>
  <img src="https://github.com/user-attachments/assets/d8515ebb-867e-4a0c-ba6c-3530e121957f" alt="Rombel Hapus" style="width: 24%;">
</div>

---

## 5. Langkah-Langkah Menjalankan Aplikasi

1. **Mengakses Halaman Aplikasi**: Buka URL melalui browser.
2. **Tampilan Awal**: Halaman `home` sebagai tampilan awal.
3. **Menu Guest**: Akses menu `home` dan `profile`.
4. **Menu Login**: Masuk untuk pengguna terdaftar.
5. **Menu Admin**: Tambah, edit, atau hapus data melalui menu lengkap.
6. **Menu Logout**: Keluar dari akun dan kembali ke halaman login.

---

## 6. Kesimpulan dan Saran

### a. Kesimpulan
Sistem ini dirancang untuk mengatasi kendala pendataan siswa di SDN Pamanukan Sebrang 1. Fitur utama seperti:
- Manajemen data siswa.
- Informasi sekolah.
- Tampilan responsif.
- Keamanan dan backup data.

Dengan sistem ini, sekolah dapat meningkatkan kualitas layanan administrasi di era digital.

### b. Saran
1. Pemeliharaan dan pembaruan sistem secara berkala.
2. Peningkatan desain antarmuka (UI/UX).
3. Optimasi kinerja sistem.
4. Pengujian dan evaluasi berkala.
5. Peningkatan keamanan data.

### Link PDF
https://github.com/FebiMaharani/Proyek-Pengembangan-APK-Web/blob/main/Projek%20Akhir/Laporan%20PPAW%20Robusta.pdf
