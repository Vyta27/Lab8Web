Nama : Navyta Budi Yulia

NIM  : 312410184

Kelas: TI.24.A2

# Lab8Web

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/bd786987-0246-4615-847d-a14a129fcc5e" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/8cc417fe-4f86-4bf6-bb18-24a717e096c1" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/e1f1f1b0-070a-4e75-b219-48e9725d3838" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/7163e4de-f248-4518-9b7e-4f13dae30d50" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/954f565a-ad61-4fa1-8d5f-10a1875ee788" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/2baf1c63-6f19-4401-9a6f-975eb3d739c5" />

<img width="1920" height="1008" alt="Image" src="https://github.com/user-attachments/assets/29a05e19-f538-4d15-86aa-c2d0d75fff52" />

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
