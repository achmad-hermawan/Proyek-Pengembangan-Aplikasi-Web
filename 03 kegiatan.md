
# Judul proyek: 
Sistem Informasi Pendataan Penjualan Di Toko Elgi

# Proyek-Pengembangan-APK-Web
Konsep Analisis Kebutuhan 

| **Fitur/Kebutuhan**             | **User**                                               | **Admin**                                            |
|----------------------------------|--------------------------------------------------------|------------------------------------------------------|
| **1. Pendaftaran Akun**          | - Mendaftar akun baru dengan email dan password        | - Tidak perlu, Admin biasanya diatur oleh sistem     |
| **2. Login/Logout**              | - Login untuk mengakses fitur pembelian produk         | - Login untuk mengelola sistem dan melihat laporan   |
| **3. Manajemen Profil**          | - Mengubah informasi profil seperti nama, alamat, dll  | - Mengelola profil admin                             |
| **4. Melihat Produk**            | - Melihat daftar produk yang tersedia untuk dibeli     | - Melihat, menambah, mengubah, atau menghapus produk |
| **5. Menambahkan ke Keranjang**  | - Menambahkan produk ke keranjang belanja              | - Tidak diperlukan                                  |
| **6. Melakukan Pembelian**       | - Membuat pesanan dan melakukan pembayaran             | - Melihat semua pesanan yang masuk                  |
| **7. Riwayat Pembelian**         | - Melihat riwayat pembelian dan status pesanan         | - Melihat riwayat semua pesanan dari semua user      |
| **8. Pembayaran**                | - Memilih metode pembayaran dan melakukan transaksi    | - Memverifikasi status pembayaran                   |
| **9. Review Produk**             | - Memberikan ulasan pada produk yang dibeli            | - Mengelola ulasan yang diberikan oleh user          |
| **10. Pengelolaan User**         | - Tidak ada akses untuk ini                            | - Melihat, mengedit, atau menghapus akun user        |
| **11. Laporan Penjualan**        | - Tidak diperlukan                                     | - Mengakses laporan penjualan harian, bulanan, tahunan|
| **12. Notifikasi Status Pesanan**| - Menerima notifikasi tentang status pesanan           | - Mengirim notifikasi kepada user tentang status pesanan |
| **13. Diskon dan Promo**         | - Melihat dan memanfaatkan diskon/promo                | - Membuat, mengelola, dan menghapus promo            |
| **14. Manajemen Stok**           | - Tidak diperlukan                                     | - Mengelola stok produk (menambah atau mengurangi)   |

# Tabel database
![Untitled](https://github.com/user-attachments/assets/c6eb86fa-a432-4eca-8b04-023f7fb86bac)


# Tabel data Penjualan
![tabel 2](https://github.com/user-attachments/assets/e1701b94-6cc4-44f5-8956-a5a497647d51)



# Rancangan Input/Output
Rancangan input dan output dalam sebuah sistem informasi penjualan mencakup elemen-elemen yang mendefinisikan apa yang akan diterima sistem (input) dan apa yang akan dihasilkan (output). Di bawah ini adalah contoh rancangan input dan output untuk sistem penjualan:

### Rancangan Input

Input yang diperlukan dalam sistem penjualan dapat dibagi menjadi beberapa kategori:

1. **Input Pelanggan**:
   - Nama Pelanggan
   - Alamat Email
   - Nomor Telepon
   - Alamat Pengiriman

2. **Input Produk**:
   - Nama Produk
   - Kategori Produk
   - Harga per Item
   - Stok yang Tersedia
   - Deskripsi Produk

3. **Input Pesanan**:
   - ID Pelanggan
   - Tanggal Pemesanan
   - Status Pesanan (misalnya: Pending, Completed, Canceled)
   - Rincian Produk (ID Produk, Jumlah)

4. **Input Pembayaran**:
   - Metode Pembayaran (misalnya: Kartu Kredit, Transfer Bank)
   - Jumlah Pembayaran
   - Tanggal Pembayaran

### Rancangan Output

Output yang dihasilkan oleh sistem penjualan juga dapat dibagi menjadi beberapa kategori:

1. **Output Laporan Penjualan**:
   - Tabel Rincian Penjualan
     - Order ID
     - Nama Pelanggan
     - Nama Produk
     - Jumlah
     - Harga per Item
     - Total Harga
     - Tanggal Pesanan
     - Status

2. **Output Konfirmasi Pesanan**:
   - Pesan konfirmasi kepada pelanggan setelah pesanan dibuat, mencakup rincian pesanan.

3. **Output Laporan Stok**:
   - Tabel yang menampilkan stok produk yang tersedia, termasuk produk yang terjual dan yang tersisa.

4. **Output Laporan Pendapatan**:
   - Total pendapatan dari penjualan dalam periode tertentu.

5. **Output Notifikasi**:
   - Notifikasi kepada admin tentang pesanan baru, pengiriman yang harus dilakukan, atau stok yang rendah.

### Contoh Format Rancangan Input dan Output

#### Rancangan Input

# Form Input Pelanggan:
![f1](https://github.com/user-attachments/assets/788f41cc-a32a-41b1-9da9-074a77ab4c3b)
# Form Input Produk:
![f2](https://github.com/user-attachments/assets/e9c155db-46cb-4dc4-999c-49bff51e7ec9)
# Form Input Pesanan:
![f3](https://github.com/user-attachments/assets/57529d1e-d67c-4a25-a40f-58321e5a0559)

#### Rancangan Output

Laporan Penjualan:
![tabel 2](https://github.com/user-attachments/assets/b31bfde0-e647-45b6-8211-57ada1336905)


Notifikasi:

Pesanan baru dari John Doe telah diterima. 
Pesanan ID: 1, Produk: Laptop, Status: Completed
