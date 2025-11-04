Nama : Navyta Budi Yulia

NIM  : 312410184
 
Kelas: TI.24.A2

# Lab8Web

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/04c211e5-061e-401d-83ec-453d8c5acc69" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/30822f96-7e97-4446-8c11-42e587706961" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/80f271e3-086f-4bb4-8055-62ca1fb0fa3d" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/52f267b2-24f6-49af-b0a9-6a8ecc672835" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/0bc17c2d-c640-41af-bfae-81df757e5fdb" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/1a1261f4-377b-4085-b635-7ca4b30f9b11" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/7522faa2-f8f3-49da-92df-5ac04f52c947" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/672f8891-1d83-49b5-a4d1-62700812b83c" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/8e8ceccc-6568-4c74-aaa5-5eb6047aef28" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/fc7b8864-aeac-4087-b4c6-916e81b5f8ca" />

1. data.js — pusat semua data

File ini adalah database sementara dalam bentuk array dan objek JavaScript.

Isinya dibagi menjadi empat bagian:

- dataPengguna → daftar akun yang bisa login (nama, email, password, role)

- dataKatalogBuku → semua data buku (kode, nama, stok, harga, cover)

- dataTracking → informasi pengiriman (nomor DO, status, ekspedisi, riwayat perjalanan)

- dataPemesanan → daftar pemesanan yang dilakukan pengguna

2. login.html dan auth.js

- Halaman pertama yang dibuka oleh pengguna.

- Pengguna mengisi email dan password.

- File auth.js memeriksa data login berdasarkan dataPengguna dari data.js.

- Jika cocok → disimpan di localStorage (data sementara browser) dengan nama userLogin.

- Setelah itu dialihkan ke dashboard.html.

- Kalau salah, muncul pesan “Email atau password salah”.

3. dashboard.html — halaman utama

Setelah login, pengguna diarahkan ke Dashboard, berisi:

- Greeting otomatis berdasarkan waktu lokal (Pagi, Siang, Sore, Malam, + nama pengguna login)

- Menu utama (navigasi):

  - Informasi Stok / Katalog

  - Laporan Pemesanan

  - Tracking Pengiriman

  - History Transaksi

Data nama pengguna diambil dari localStorage (userLogin) yang disimpan waktu login.

4. stok.html dan stok.js
   
Halaman ini menampilkan seluruh katalog buku yang ada di dataKatalogBuku. Fitur utama:

- Menampilkan daftar semua buku (judul, stok, harga, dan gambar cover).

- Bisa menambah buku baru secara manual (input di bawah tabel).

- Buku baru akan ditambahkan langsung ke array dataKatalogBuku dan tampil di layar (tanpa reload).

- Fungsi ini hanya disimpan di memori browser (tidak ke database).

  5. checkout.html dan checkout.js

Halaman ini digunakan untuk form pemesanan buku. Fungsi:

- Pengguna mengisi data pemesan (nama, alamat, no HP).

- Memilih buku dari daftar katalog (yang diambil dari dataKatalogBuku).

- Mengisi jumlah dan metode pembayaran.

- Ketika tombol “Tambah ke Daftar Pesanan” diklik:

    - Data dimasukkan ke array dataPemesanan

    - Ditampilkan ke dalam tabel daftar pesanan

    - Total harga otomatis dihitung dan ditampilkan di bawah tabel

Tujuannya untuk mensimulasikan proses pemesanan sebelum data dikirim ke penjual.

6. tracking.html dan tracking.js

Halaman ini digunakan untuk melacak status pengiriman berdasarkan nomor DO (Delivery Order). Cara kerjanya:

- Pengguna mengetik nomor DO di input dan klik tombol “Cari”.

- Script akan mencari nomor tersebut di dataTracking.

- Jika ditemukan → tampilkan informasi lengkap:

    - Nama pemesan

    - Ekspedisi

    - Tanggal kirim

    - Jenis paket

    - Total pembayaran

    - Status pengiriman

    - Progress bar (menunjukkan persentase perjalanan)

    - Riwayat perjalanan (log setiap tahap pengiriman)

Progress bar otomatis:

- Jika status “Selesai Antar” → progress 100% hijau

- Jika Dalam Perjalanan → progress sesuai jumlah log perjalanan (misal 3 log = 75%)

- Semua dihitung otomatis tanpa ubah data.js

7. history.html

- Halaman terakhir — menampilkan riwayat transaksi yang sudah selesai.

Logika penting:

- Mengambil data dari dataTracking

- Menyaring hanya yang status-nya “Selesai Antar” atau “Pesanan Selesai”

Menampilkan tabel berisi:

- Nomor DO

- Nama Pemesan

- Ekspedisi

- Tanggal Kirim

- Total

- Status

- Ada juga tombol “Kembali ke Dashboard” untuk navigasi balik.
