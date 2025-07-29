Sistem Manajemen Inventori Toko Kecil
Aplikasi sederhana untuk mencatat dan mengelola data inventori barang pada sebuah toko kecil.

1. Dokumentasi Teknis
Struktur File/Kode
Aplikasi ini terdiri dari satu file Python utama, inventory_app.py, dan satu file data inventory.json yang akan dibuat secara otomatis saat aplikasi dijalankan dan data ditambahkan.

inventory_app.py:

Berisi semua logika aplikasi, termasuk fungsi untuk menambah, menampilkan, mengedit, menghapus, mencari, mengekspor, dan membuat laporan barang.

Fungsi main() mengelola menu interaktif dan alur aplikasi.

inventory.json:

File ini digunakan untuk menyimpan data inventori secara persisten dalam format JSON. Setiap kali aplikasi ditutup dan dibuka kembali, data akan tetap tersedia.

inventory_report.csv (Opsional):

File ini akan dibuat ketika fitur ekspor ke CSV digunakan, berisi data inventori dalam format CSV.

Library yang Digunakan
Aplikasi ini menggunakan library standar Python berikut:

json: Digunakan untuk membaca dan menulis data inventori ke/dari file inventory.json. Ini memastikan data tetap ada meskipun aplikasi ditutup.

csv: Digunakan untuk mengekspor data inventori ke format CSV, yang mudah dibuka di spreadsheet seperti Microsoft Excel atau Google Sheets.

os: Digunakan untuk memeriksa keberadaan file inventory.json saat aplikasi pertama kali dijalankan atau saat memuat data.

Diagram Alur Kerja Aplikasi
+----------------+
|     Mulai      |
+----------------+
        |
        v
+----------------+
| Muat Inventori |
| (inventory.json)|
+----------------+
        |
        v
+----------------+
|   Tampilkan    |
|      Menu      |
+----------------+
        |
        v
+----------------+
|   Pilih Opsi   |
+----------------+
        |
        |---- 1. Tambah Barang ----> +----------------+
        |                            |   Input Data   |
        |                            | (Nama, Stok, Harga) |
        |                            +----------------+
        |                                   |
        |                                   v
        |                            +----------------+
        |                            | Simpan Data    |
        |                            | ke Inventori   |
        |                            +----------------+
        |                                   |
        |                                   v
        |                            +----------------+
        |                            | Simpan Inventori|
        |                            | (inventory.json)|
        |                            +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 2. Tampilkan Daftar Barang --> +----------------+
        |                                    | Tampilkan Semua|
        |                                    | Barang         |
        |                                    +----------------+
        |                                           |
        |-------------------------------------------+
        |
        |---- 3. Edit Barang --------> +----------------+
        |                             | Pilih Barang   |
        |                             | (berdasarkan No.)|
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Input Data Baru|
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Perbarui Data  |
        |                             | di Inventori   |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Simpan Inventori|
        |                             | (inventory.json)|
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 4. Hapus Barang -------> +----------------+
        |                             | Pilih Barang   |
        |                             | (berdasarkan No.)|
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Konfirmasi     |
        |                             | Penghapusan    |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Hapus Data     |
        |                             | dari Inventori |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Simpan Inventori|
        |                             | (inventory.json)|
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 5. Cari Barang --------> +----------------+
        |                             | Input Nama     |
        |                             | Barang Dicari  |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Tampilkan Hasil|
        |                             | Pencarian      |
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 6. Ekspor ke CSV ------> +----------------+
        |                             | Tulis Data     |
        |                             | ke inventory_report.csv |
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 7. Laporan Inventori ----> +----------------+
        |                               | Hitung Total   |
        |                               | Barang & Nilai |
        |                               +----------------+
        |                                     |
        |-------------------------------------+
        |
        |---- 8. Keluar -------------------> +----------------+
        |                                    |     Selesai    |
        +------------------------------------+----------------+


2. User Manual
Cara Menjalankan Aplikasi
Pastikan Python Terinstal: Anda perlu memiliki Python 3.x terinstal di komputer Anda. Anda bisa mengunduhnya dari python.org.

Simpan Kode: Salin kode Python yang disediakan ke dalam sebuah file dan simpan dengan nama inventory_app.py (atau nama lain dengan ekstensi .py).

Buka Terminal/Command Prompt: Navigasikan ke direktori tempat Anda menyimpan file inventory_app.py menggunakan terminal (Linux/macOS) atau Command Prompt/PowerShell (Windows).

Contoh: cd C:\Users\NamaAnda\Documents\ProyekInventori

Jalankan Aplikasi: Ketik perintah berikut dan tekan Enter:

python inventory_app.py


Aplikasi akan menampilkan menu utama di terminal.

Contoh Input
Setelah aplikasi berjalan, Anda akan melihat menu utama. Berikut adalah contoh interaksi:

Menambah Barang:

Pilih opsi 1 (Tambah Barang).

Aplikasi akan meminta:

Masukkan Nama Barang: (misal: Honda Beat)

Masukkan Stok Barang: (misal: 2)

Masukkan Harga Barang: (misal: 12000000)

Barang akan ditambahkan dan disimpan.

Menampilkan Daftar Barang:

Pilih opsi 2 (Tampilkan Daftar Barang).

Aplikasi akan menampilkan semua barang yang ada di inventori dalam bentuk tabel.

Cara Edit & Hapus Data
Mengedit Data Barang:

Pilih opsi 3 (Edit Barang).

Aplikasi akan menampilkan daftar barang dengan nomor urut.

Masukkan Nomor Barang yang ingin diedit: (misal: 1 untuk barang pertama).

Aplikasi akan menampilkan detail barang tersebut dan meminta input untuk nama, stok, dan harga baru.

Anda bisa mengosongkan input (tekan Enter langsung) jika Anda tidak ingin mengubah nilai tersebut.

Setelah Anda memasukkan perubahan, data barang akan diperbarui.

Menghapus Data Barang:
11. Pilih opsi 4 (Hapus Barang).
12. Aplikasi akan menampilkan daftar barang dengan nomor urut.
13. Masukkan Nomor Barang yang ingin dihapus: (misal: 2 untuk barang kedua).
14. Aplikasi akan meminta konfirmasi: Anda yakin ingin menghapus 'Nama Barang'? (ya/tidak):
* Ketik ya dan tekan Enter untuk mengonfirmasi penghapusan.
* Ketik tidak atau apapun selain ya untuk membatalkan.
15. Jika dikonfirmasi, barang akan dihapus dari inventori.

Fitur Bonus
Pencarian Barang:

Pilih opsi 5 (Cari Barang).

Masukkan Nama Barang yang dicari: (misal: Honda Beat).

Aplikasi akan menampilkan semua barang yang namanya mengandung kata "buku" (tidak peka huruf besar/kecil).

Ekspor ke CSV:

Pilih opsi 6 (Ekspor ke CSV).

Data inventori akan disimpan ke file bernama inventory_report.csv di direktori yang sama dengan inventory_app.py.

Laporan Ringkas:

Pilih opsi 7 (Laporan Inventori).

Aplikasi akan menampilkan ringkasan seperti jumlah total barang unik, total stok, dan total nilai inventori.

3. Pengujian & Evaluasi (Contoh Skenario)
Berikut adalah contoh skenario pengujian yang dapat Anda lakukan:

Skenario 1: Tambah dan Hapus Barang
Mulai Aplikasi: Jalankan python inventory_app.py.

Tambah Barang 1:

Pilih 1.

Nama: Honda Beat, Stok: 2, Harga: 12000000.

Verifikasi pesan "Barang 'Pensil' berhasil ditambahkan."

Tampilkan Daftar Barang:

Pilih 1.

Pastikan "Honda Beat" muncul dalam daftar dengan stok dan harga yang benar.

Hapus Barang 1 (Honda Beat):

Pilih 4.

Masukkan nomor 1 (untuk Honda Beat.

Konfirmasi ya.

Verifikasi pesan "Barang 'Honda BEat' berhasil dihapus."

Tampilkan Daftar Barang:

Pilih 2.

Pastikan hanya "Penghapus" yang tersisa dalam daftar.

Keluar: Pilih 8.

Jalankan Ulang Aplikasi: Jalankan python inventory_app.py lagi.

Tampilkan Daftar Barang:

Pilih 2.

Pastikan "Honda Beat" masih ada, menunjukkan data berhasil disimpan dan dimuat.

Skenario 2: Edit Barang dan Laporan
Mulai Aplikasi: Jalankan python inventory_app.py. (Pastikan ada data, jika tidak, tambahkan beberapa barang terlebih dahulu).

Tambah Barang (jika inventori kosong):

Pilih 1. Nama: Honda Beat, Stok: 2, Harga: 12000000.

Tampilkan Daftar Barang:

Pilih 2. Catat nomor urut untuk "Honda Beat".

Edit Barang "Honda Beat":

Pilih 3. Masukkan nomor urut "1".

Nama Baru: (kosongkan)

Stok Baru: 3

Harga Baru: (kosongkan)

Tampilkan Daftar Barang:

Pilih 1. Pastikan "Honda Beat" sekarang memiliki Stok 3 dan Harga 12000000.

Generate Laporan:

Pilih 7.

Periksa Jumlah Barang Unik, Total Stok Semua Barang, dan Total Nilai Inventori sesuai dengan data yang ada (termasuk perubahan pada "Buku").

Keluar: Pilih 8.
