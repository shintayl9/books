Nama    : Shinta Yulistiana 
NIM     : 362358302076
Kelas   : 2A TRPL


#11 | Pemrograman Asynchronous
Praktikum 1: Mengunduh Data dari Web Service (API)

Langkah 1: Buat Project Baru
Menambahkan dependensi http dengan mengetik perintah flutter pub add http.
![Screenshot books](images/image%201.png)

Langkah 2: Cek file pubspec.yaml
![Screenshot books](images/image%202.png)

Langkah 3: Buka file main.dart
Mengetik kode dan menambahkan nama panggilan pada title app sebagai identitas hasil pekerjaan.
![Screenshot books](images/image%203.png)

Langkah 4: Tambah method getData()
![Screenshot books](images/image%204.png)
![Screenshot books](images/image%205.png)

Langkah 5: Tambah kode di ElevatedButton
![Screenshot books](images/image%206.png)
Maksud kode langkah 5 tersebut terkait substring dan catchError
- substring(0, 450) digunakan untuk membatasi data dari API agar hanya menampilkan 450 karakter pertama agar data yang ditampilkan pada UI tidak terlalu panjang.
- catchError digunakan untuk menangani error yang mungkin akan terjadi saat memanggil fungsi getData(). Jika terjadi error, maka blok yang ada di catchError akan dijalankan untuk memastikan aplikasi tidak crash.
![Screenshot books](images/asynchronous.gif)