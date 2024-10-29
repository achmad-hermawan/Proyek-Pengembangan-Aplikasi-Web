# Pertemuan 5
## Tampilan Create Data Pelanggan
### Program Sales

    <?php
        $host = 'localhost'; 
        $db_name = 'tabel laptop'; 
        $username = 'root'; 
        $password = ''; 
        
        
        $conn = new mysqli($host, $username, $password, $db_name);
        
        
        if ($conn->connect_error) {
            die("Koneksi gagal: " . $conn->connect_error);
        }
        
        if (isset($_POST['delete'])) {
            $order_id = (int)$_POST['order_id'];
        
            
            $sql = "DELETE FROM sales WHERE order_id = $order_id";
            if ($conn->query($sql) === TRUE) {
                header("Location: index.php?message=Data berhasil dihapus."); 
                exit();
            } else {
                echo "Error: " . $conn->error;
            }
        }
        
        $sql = "SELECT * FROM sales";
        $result = $conn->query($sql);
    ?>
    
    <!DOCTYPE html>
    <html lang="id">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Data Penjualan</title>
        <style>
            table {
                width: 100%;
                border-collapse: collapse;
            }
            th, td {
                padding: 10px;
                text-align: left;
                border: 1px solid #ddd;
            }
            th {
                background-color: #f2f2f2;
            }
            .btn-edit {
                background-color: yellow;
                padding: 5px 10px;
                border: none;
                color: black;
                cursor: pointer;
                text-decoration: none;
            }
            .btn-hapus {
                background-color: red;
                padding: 5px 10px;
                border: none;
                color: white;
                cursor: pointer;
            }
            .btn-tambah {
                background-color: #007bff;
                color: white;
                padding: 8px 12px;
                text-decoration: none;
                border-radius: 5px;
                display: inline-block;
                margin-bottom: 10px;
            }
        </style>
    </head>
    <body>

    <h2>Data Penjualan</h2>

    <!-- Tombol Tambah Penjualan -->
    <a href="form_tambah.php" class="btn-tambah">Tambah Penjualan</a>

    <?php
    if ($result->num_rows > 0) {
        echo "<table>
                <thead>
                    <tr>
                        <th>Order ID</th>
                        <th>Customer Name</th>
                        <th>Product Name</th>
                        <th>Quantity</th>
                        <th>Price per Item</th>
                        <th>Total Price</th>
                        <th>Order Date</th>
                        <th>Status</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>";

        // Mengambil dan menampilkan setiap baris data
        while ($row = $result->fetch_assoc()) {
            echo "<tr>
                    <td>{$row['order_id']}</td>
                    <td>{$row['customer_name']}</td>
                    <td>{$row['product_name']}</td>
                    <td>{$row['quantity']}</td>
                    <td>{$row['price_per_item']}</td>
                    <td>{$row['total_price']}</td>
                    <td>{$row['order_date']}</td>
                    <td>{$row['status']}</td>
                    <td>
                        <a href='edit.php?order_id={$row['order_id']}' class='btn-edit'>Edit</a>
                        <form method='POST' style='display:inline;'>
                            <input type='hidden' name='order_id' value='{$row['order_id']}'>
                            <input type='submit' name='delete' class='btn-hapus' value='Hapus' onclick='return confirm(\"Apakah Anda yakin ingin menghapus?\");'>
                        </form>
                    </td>
                  </tr>";
        }

        echo "</tbody></table>";
    } else {
        echo "Tidak ada data penjualan.";
    }

    // Tutup koneksi
    $conn->close();
    ?>

    </body>
    </html>

Output
  ![data awal](https://github.com/user-attachments/assets/6a46a865-7d80-4d98-a1f1-d60c524fa985)

### Program Form Crate Data
    <?php
    // Konfigurasi koneksi database
    $host = 'localhost'; // Ganti dengan host database Anda jika perlu
    $db_name = 'tabel laptop'; // Nama database
    $username = 'root'; // Ganti dengan username database Anda
    $password = ''; // Ganti dengan password database Anda
    
    // Membuat koneksi ke database
    $conn = new mysqli($host, $username, $password, $db_name);
    
    // Cek koneksi
    if ($conn->connect_error) {
        die("Koneksi gagal: " . $conn->connect_error);
    }
    
    // Proses penyimpanan data
    if ($_SERVER['REQUEST_METHOD'] == 'POST') {
        $customer_name = $_POST['customer_name'];
        $product_name = $_POST['product_name'];
        $quantity = $_POST['quantity'];
        $price_per_item = $_POST['price_per_item'];
        $total_price = $quantity * $price_per_item;
        $order_date = $_POST['order_date'];
        $status = $_POST['status'];
    
        $sql = "INSERT INTO sales (customer_name, product_name, quantity, price_per_item, total_price, order_date, status) 
                VALUES ('$customer_name', '$product_name', $quantity, $price_per_item, $total_price, '$order_date', '$status')";
    
        if ($conn->query($sql) === TRUE) {
            header("Location: index.php"); // Ganti dengan nama file utama Anda
            exit();
        } else {
            echo "Error: " . $sql . "<br>" . $conn->error;
        }
    }
    
    $conn->close();
    ?>
    
    <!DOCTYPE html>
    <html lang="id">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Tambah Penjualan</title>
        <style>
            body {
                font-family: Arial, sans-serif;
                margin: 0;
                padding: 20px;
                background-color: #f4f4f4;
            }
            h2 {
                color: #333;
            }
            form {
                background: white;
                padding: 20px;
                border-radius: 8px;
                box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            }
            label {
                margin-top: 10px;
                display: block;
            }
            input[type="text"], input[type="number"], input[type="date"], select {
                width: calc(100% - 20px);
                padding: 10px;
                margin: 5px 0;
                border: 1px solid #ccc;
                border-radius: 4px;
            }
            input[type="submit"] {
                background-color: #28a745; /* Warna Hijau */
                color: white;
                padding: 10px 15px;
                border: none;
                border-radius: 4px;
                cursor: pointer;
                font-size: 16px;
                transition: background-color 0.3s;
            }
            input[type="submit"]:hover {
                background-color: #218838; /* Warna Hijau Gelap */
            }
            a {
                display: inline-block;
                margin-top: 10px;
                text-decoration: none;
                color: white;
                background-color: #007bff; /* Warna Biru */
                padding: 10px 15px;
                border-radius: 4px;
                transition: background-color 0.3s;
            }
            a:hover {
                background-color: #0056b3; /* Warna Biru Gelap */
            }
        </style>
    </head>
    <body>
        <h2>Tambah Penjualan</h2>
        <form method="POST">
            <label>Nama Pelanggan:</label>
            <input type="text" name="customer_name" required>
        
        <label>Nama Produk:</label>
        <input type="text" name="product_name" required>
        
        <label>Kuantitas:</label>
        <input type="number" name="quantity" required>
        
        <label>Harga per Item:</label>
        <input type="number" name="price_per_item" required>
        
        <label>Tanggal Pemesanan:</label>
        <input type="date" name="order_date" required>
        
        <label>Status:</label>
        <select name="status" required>
            <option value="Pending">Pending</option>
            <option value="Completed">Completed</option>
            <option value="Canceled">Canceled</option>
        </select>
        
        <input type="submit" value="Simpan">
    </form>
    <a href="index.php">Kembali</a>
    </body>
    </html>

Output Tambah Data Dan setelah Di Tambah
  ![tambah data](https://github.com/user-attachments/assets/2bd6ecf7-a449-469a-a110-716f76d2f019)
  ![data setelah di tambah](https://github.com/user-attachments/assets/2412eb76-06c8-41b0-8524-01aa7a52ed70)

## Tampilan Edit Data Pelanggan
### Program PHP
    <?php
    $host = 'localhost'; 
    $db_name = 'tabel laptop'; 
    $username = 'root'; 
    $password = ''; 
    
    
    $conn = new mysqli($host, $username, $password, $db_name);
    
    
    if ($conn->connect_error) {
        die("Koneksi gagal: " . $conn->connect_error);
    }
    
    if (isset($_POST['delete'])) {
        $order_id = (int)$_POST['order_id'];
    
        
        $sql = "DELETE FROM sales WHERE order_id = $order_id";
        if ($conn->query($sql) === TRUE) {
            header("Location: index.php?message=Data berhasil dihapus."); 
            exit();
        } else {
            echo "Error: " . $conn->error;
        }
    }
    
    $sql = "SELECT * FROM sales";
    $result = $conn->query($sql);
    ?>
    
    <!DOCTYPE html>
    <html lang="id">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Data Penjualan</title>
        <style>
            table {
                width: 100%;
                border-collapse: collapse;
            }
            th, td {
                padding: 10px;
                text-align: left;
                border: 1px solid #ddd;
            }
            th {
                background-color: #f2f2f2;
            }
            .btn-edit {
                background-color: yellow;
                padding: 5px 10px;
                border: none;
                color: black;
                cursor: pointer;
                text-decoration: none;
            }
            .btn-hapus {
                background-color: red;
                padding: 5px 10px;
                border: none;
                color: white;
                cursor: pointer;
            }
            .btn-tambah {
                background-color: #007bff;
                color: white;
                padding: 8px 12px;
                text-decoration: none;
                border-radius: 5px;
                display: inline-block;
                margin-bottom: 10px;
            }
        </style>
    </head>
    <body>

    <h2>Data Penjualan</h2>

    <!-- Tombol Tambah Penjualan -->
    <a href="form_tambah.php" class="btn-tambah">Tambah Penjualan</a>

    <?php
    if ($result->num_rows > 0) {
        echo "<table>
                <thead>
                    <tr>
                        <th>Order ID</th>
                        <th>Customer Name</th>
                        <th>Product Name</th>
                        <th>Quantity</th>
                        <th>Price per Item</th>
                        <th>Total Price</th>
                        <th>Order Date</th>
                        <th>Status</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>";

        // Mengambil dan menampilkan setiap baris data
        while ($row = $result->fetch_assoc()) {
            echo "<tr>
                    <td>{$row['order_id']}</td>
                    <td>{$row['customer_name']}</td>
                    <td>{$row['product_name']}</td>
                    <td>{$row['quantity']}</td>
                    <td>{$row['price_per_item']}</td>
                    <td>{$row['total_price']}</td>
                    <td>{$row['order_date']}</td>
                    <td>{$row['status']}</td>
                    <td>
                        <a href='edit.php?order_id={$row['order_id']}' class='btn-edit'>Edit</a>
                        <form method='POST' style='display:inline;'>
                            <input type='hidden' name='order_id' value='{$row['order_id']}'>
                            <input type='submit' name='delete' class='btn-hapus' value='Hapus' onclick='return confirm(\"Apakah Anda yakin ingin menghapus?\");'>
                        </form>
                    </td>
                  </tr>";
        }

        echo "</tbody></table>";
    } else {
        echo "Tidak ada data penjualan.";
    }

    // Tutup koneksi
    $conn->close();
    ?>
    
    </body>
    </html>

Output
   ![sebelum edit](https://github.com/user-attachments/assets/73b373bb-4304-4e29-8faf-4e46fa4dff31)
### Program Edit Data
    <?php
    // Konfigurasi koneksi database
    $host = 'localhost'; // Ganti dengan host database Anda jika perlu
    $db_name = 'tabel laptop'; // Nama database
    $username = 'root'; // Ganti dengan username database Anda
    $password = ''; // Ganti dengan password database Anda
    
    // Membuat koneksi ke database
    $conn = new mysqli($host, $username, $password, $db_name);
    
    // Cek koneksi
    if ($conn->connect_error) {
        die("Koneksi gagal: " . $conn->connect_error);
    }
    
    // Ambil data untuk diedit
    $order_id = $_GET['order_id'];
    $sql = "SELECT * FROM sales WHERE order_id = $order_id";
    $result = $conn->query($sql);
    $row = $result->fetch_assoc();
    
    // Proses update data
    if ($_SERVER['REQUEST_METHOD'] == 'POST') {
        $customer_name = $_POST['customer_name'];
        $product_name = $_POST['product_name'];
        $quantity = $_POST['quantity'];
        $price_per_item = $_POST['price_per_item'];
        $total_price = $quantity * $price_per_item;
        $order_date = $_POST['order_date'];
        $status = $_POST['status'];
    
        $sql = "UPDATE sales SET customer_name='$customer_name', product_name='$product_name', quantity=$quantity, 
                price_per_item=$price_per_item, total_price=$total_price, order_date='$order_date', status='$status' 
                WHERE order_id=$order_id";
    
        if ($conn->query($sql) === TRUE) {
            header("Location: index.php"); // Ganti dengan nama file utama Anda
            exit();
        } else {
            echo "Error: " . $sql . "<br>" . $conn->error;
        }
    }
    
    $conn->close();
    ?>
    
    <!DOCTYPE html>
    <html lang="id">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Edit Penjualan</title>
        <style>
            body {  
                font-family: Arial, sans-serif;
                margin: 0;
                padding: 20px;
                background-color: #f4f4f4;
            }
            h2 {
                color: #333;
            }
            form {
                background: white;
                padding: 20px;
                border-radius: 8px;
                box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            }
            label {
                margin-top: 10px;
                display: block;
            }
            input[type="text"], input[type="number"], input[type="date"], select {
                width: calc(100% - 20px);
                padding: 10px;
                margin: 5px 0;
                border: 1px solid #ccc;
                border-radius: 4px;
            }
            input[type="submit"] {
                background-color: #007bff; /* Warna Biru */
                color: white;
                padding: 10px 15px;
                border: none;
                border-radius: 4px;
                cursor: pointer;
                font-size: 16px;
                transition: background-color 0.3s;
            }
            input[type="submit"]:hover {
                background-color: #0056b3; /* Warna Biru Gelap */
            }
            a {
                display: inline-block;
                margin-top: 10px;
                text-decoration: none;
                color: white;
                background-color: #28a745; /* Warna Hijau */
                padding: 10px 15px;
                border-radius: 4px;
                transition: background-color 0.3s;
            }
            a:hover {
                background-color: #218838; /* Warna Hijau Gelap */
            }
        </style>
    </head>
    <body>
        <h2>Edit Penjualan</h2>
        <form method="POST">
            <label>Nama Pelanggan:</label>
            <input type="text" name="customer_name" value="<?= $row['customer_name'] ?>" required>
        
        <label>Nama Produk:</label>
        <input type="text" name="product_name" value="<?= $row['product_name'] ?>" required>
        
        <label>Kuantitas:</label>
        <input type="number" name="quantity" value="<?= $row['quantity'] ?>" required>
        
        <label>Harga per Item:</label>
        <input type="number" name="price_per_item" value="<?= $row['price_per_item'] ?>" required>
        
        <label>Tanggal Pemesanan:</label>
        <input type="date" name="order_date" value="<?= $row['order_date'] ?>" required>
        
        <label>Status:</label>
        <select name="status" required>
            <option value="Pending" <?= $row['status'] == 'Pending' ? 'selected' : '' ?>>Pending</option>
            <option value="Completed" <?= $row['status'] == 'Completed' ? 'selected' : '' ?>>Completed</option>
            <option value="Canceled" <?= $row['status'] == 'Canceled' ? 'selected' : '' ?>>Canceled</option>
        </select>
        
        <input type="submit" value="Update">
    </form>
    <a href="index.php">Kembali</a>
    </body>
    </html>

Output Proses Edit Data Dan Setelah Di Edit
   ![proses edit](https://github.com/user-attachments/assets/ca503a94-5e3a-41d2-a3e3-53e2e4feea39)
  ![sesudah edit](https://github.com/user-attachments/assets/dab11a2b-f764-485f-9d09-c57127def1e9)

## Tampilan Delete Data Pelanggan
### Program PHP
    <?php
    $host = 'localhost'; 
    $db_name = 'tabel laptop'; 
    $username = 'root'; 
    $password = ''; 
    
    
    $conn = new mysqli($host, $username, $password, $db_name);
    
    
    if ($conn->connect_error) {
        die("Koneksi gagal: " . $conn->connect_error);
    }
    
    if (isset($_POST['delete'])) {
        $order_id = (int)$_POST['order_id'];
    
        
        $sql = "DELETE FROM sales WHERE order_id = $order_id";
        if ($conn->query($sql) === TRUE) {
            header("Location: index.php?message=Data berhasil dihapus."); 
            exit();
        } else {
            echo "Error: " . $conn->error;
        }
    }
    
    $sql = "SELECT * FROM sales";
    $result = $conn->query($sql);
    ?>
    
    <!DOCTYPE html>
    <html lang="id">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Data Penjualan</title>
        <style>
            table {
                width: 100%;
                border-collapse: collapse;
            }
            th, td {
                padding: 10px;
                text-align: left;
                border: 1px solid #ddd;
            }
            th {
                background-color: #f2f2f2;
            }
            .btn-edit {
                background-color: yellow;
                padding: 5px 10px;
                border: none;
                color: black;
                cursor: pointer;
                text-decoration: none;
            }
            .btn-hapus {
                background-color: red;
                padding: 5px 10px;
                border: none;
                color: white;
                cursor: pointer;
            }
            .btn-tambah {
                background-color: #007bff;
                color: white;
                padding: 8px 12px;
                text-decoration: none;
                border-radius: 5px;
                display: inline-block;
                margin-bottom: 10px;
            }
        </style>
    </head>
    <body>

    <h2>Data Penjualan</h2>

    <!-- Tombol Tambah Penjualan -->
    <a href="form_tambah.php" class="btn-tambah">Tambah Penjualan</a>

    <?php
    if ($result->num_rows > 0) {
        echo "<table>
                <thead>
                    <tr>
                        <th>Order ID</th>
                        <th>Customer Name</th>
                        <th>Product Name</th>
                        <th>Quantity</th>
                        <th>Price per Item</th>
                        <th>Total Price</th>
                        <th>Order Date</th>
                        <th>Status</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>";

        // Mengambil dan menampilkan setiap baris data
        while ($row = $result->fetch_assoc()) {
            echo "<tr>
                    <td>{$row['order_id']}</td>
                    <td>{$row['customer_name']}</td>
                    <td>{$row['product_name']}</td>
                    <td>{$row['quantity']}</td>
                    <td>{$row['price_per_item']}</td>
                    <td>{$row['total_price']}</td>
                    <td>{$row['order_date']}</td>
                    <td>{$row['status']}</td>
                    <td>
                        <a href='edit.php?order_id={$row['order_id']}' class='btn-edit'>Edit</a>
                        <form method='POST' style='display:inline;'>
                            <input type='hidden' name='order_id' value='{$row['order_id']}'>
                            <input type='submit' name='delete' class='btn-hapus' value='Hapus' onclick='return confirm(\"Apakah Anda yakin ingin menghapus?\");'>
                        </form>
                    </td>
                  </tr>";
        }

        echo "</tbody></table>";
    } else {
        echo "Tidak ada data penjualan.";
    }

    // Tutup koneksi
    $conn->close();
    ?>

    </body>
    </html>
  Output Data Pelanggan
   ![sebelum hapus](https://github.com/user-attachments/assets/177b6b91-6ba8-4905-aca2-a02daba9ca4c)
   
### Program Index.PHP yang di gunakan untuk menghapus data
     <?php
  	if (!empty($_SERVER['HTTPS']) && ('on' == $_SERVER['HTTPS'])) {
  		$uri = 'https://';
  	} else {
  		$uri = 'http://';
  	}
  	$uri .= $_SERVER['HTTP_HOST'];
  	header('Location: '.$uri.'/dashboard/');
  	exit;
    ?>
Output Proses Delete Data Pelanggan Dam Sesudah Di Delete
   ![proses hapus](https://github.com/user-attachments/assets/94f9d90a-4d16-468a-922e-f1041996e020)
   ![sesudah hapus](https://github.com/user-attachments/assets/ad218142-b86c-477f-958f-8563af10e525)



   


   
   








