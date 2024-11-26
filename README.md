Nama : Shinta Yulistiana
NIM : 362358302076
Kelas : 2A TRPL

#11 | Pemrograman Asynchronous

**Praktikum 1: Mengunduh Data dari Web Service (API)**

Langkah 1: Buat Project Baru
Menambahkan dependensi http dengan mengetik perintah flutter pub add http.
![Screenshot books](images/image%201.png)

Langkah 2: Cek file pubspec.yaml

![Screenshot books](images/image%202.png)

Langkah 3: Buka file main.dart

Mengetik kode dan menambahkan nama panggilan pada title app sebagai identitas hasil pekerjaan.
![Screenshot books](images/image%203.png)

**Soal 1**

![Screenshot books](images/image%203.png)

Langkah 4: Tambah method getData()
![Screenshot books](images/image%204.png)
![Screenshot books](images/image%205.png)

**Soal 2**
![Screenshot books](images/image%2037.png)
![Screenshot books](images/image%205.png)

Langkah 5: Tambah kode di ElevatedButton
![Screenshot books](images/image%206.png)
Maksud kode langkah 5 tersebut terkait substring dan catchError

**Soal 3**

- substring(0, 450) digunakan untuk membatasi data dari API agar hanya menampilkan 450 karakter pertama agar data yang ditampilkan pada UI tidak terlalu panjang.
- catchError digunakan untuk menangani error yang mungkin akan terjadi saat memanggil fungsi getData(). Jika terjadi error, maka blok yang ada di catchError akan dijalankan untuk memastikan aplikasi tidak crash.
  ![Screenshot books](images/asynchronous.gif)

**Praktikum 2: Menggunakan await/async untuk menghindari callbacks**

Langkah 1: Buka file main.dart

Menambahkan tiga method berisi kode seperti berikut di dalam class \_FuturePageState.
![Screenshot books](images/image%207.png)

Langkah 2: Tambah method count()
![Screenshot books](images/image%208.png)

Langkah 3: Panggil count()
![Screenshot books](images/image%209.png)

Langkah 4: Run
![Screenshot books](images/image%2038.png)

**Soal 4**

Maksud kode langkah 1 dan 2

- Maksud kode langkah 1 adalah mendefinisikan tiga metode asynchronous masing-masing mengembalikan angka setelah 3 detik. Future.delayed digunakan untuk penundaan (delay) dalam simulasi pemanggilan API yang memerlukan waktu untuk merespon.
- Maksud kode langkah 2 adalah mendefinisikan sebuah metode count() yang akan memanggil ketiga fungsi yang telah didefinisikan sebelumnya dan menghitung totalnya.count() akan menunggu hasil dari returnOneAsync(), returnTwoAsync(), returnThreeAsync() yang setelah 3 detik akan mengembalikan angka 1, 2, dan 3 lalu nilai kemudian ditambahkan ke total. Setelah ketiga nilai dijumlah, setState dipanggil untuk memperbarui UI dengan nilai total yang baru dihitung. total diubah menjadi tipe String agar dapat ditampilkan dalam widget Text.
- ![Screenshot books](images/asynchronous1.gif)

**Praktikum 3: Menggunakan Completer di Future**

Langkah 1: Buka main.dart
![Screenshot books](images/image%2010.png)

Langkah 2: Tambahkan variabel dan method
![Screenshot books](images/image%2011.png)

Langkah 3: Ganti isi kode onPressed()
![Screenshot books](images/image%2012.png)

Langkah 4:
![Screenshot books](images/image%2039.png)

**Soal 5**

- Maksud kode langkah 2 adalah mendefinisikan 2 fungsi yaitu getNumber() dan calculate() yang berfungsi untuk mengatur pengembalian nilai dengan mengunakan Completer dalam Dart yang digunakan untuk menangani nilai yang akan datang (asynchronous) yang memungkinkan untuk kapan dan bagaimana nilai tersebut diselesaikan dan dikembalikan dalam operasi asynchronous.
- ![Screenshot books](images/asynchronous2.gif)

Langkah 5: Ganti method calculate()
![Screenshot books](images/image%2013.png)

Langkah 6: Pindah ke onPressed()

Mengganti kode
![Screenshot books](images/image%2014.png)

**Soal 6**

- Maksud perbedaan kode langkah 2 dengan langkah 5-6 adalah langkah 2 hanya menangani penyelesaian normal tanpa mempertimbangkan kemungkinan error sementara langkah 5 dan 6 menambah kemampuan untuk menangani kesalahan dengan baik dalam proses asynchronous.
  ![Screenshot books](images/asynchronous3.gif)

**Praktikum 4: Memanggil Future secara paralel**

Langkah 1: Buka file main.dart

Menambahkan method ke dalam class \_FuturePageState
![Screenshot books](images/image%2015.png)

Langkah 2: Edit onPressed()
![Screenshot books](images/image%2016.png)

Langkah 3: Run

**Soal 7**
![Screenshot books](images/asynchronous4.gif)

Langkah 4: Ganti variabel futureGroup
![Screenshot books](images/image%2017.png)

**Soal 8**

Maksud perbedaan kode langkah 1 dan 4

- Pada langkah 1 menggunakan FutureGroup, lebih fleksibel dan memungkinkan untuk menangani grup Future secara lebih eksplisit dan kompleks, meskipun lebih rumit.
- Pada langkah 4 menggunakan Future.wait, lebih sederhana dan lebih mudah dipahami untuk skenario dasar dimana hanya ingin menunggu beberapa Future untuk menyelesaikan dan mendapatkan hasilnya secara bersamaan dalam bentuk List.

**Praktikum 5: Menangani Respon Error pada Async Code**

Langkah 1: Buka file main.dart

Menambahkan method ke dalam class \_FuturePageState
![Screenshot books](images/image%2018.png)

Langkah 2: ElevatedButton

Mengganti kode
![Screenshot books](images/image%2019.png)

Langkah 3: Run
![Screenshot books](images/image%2020.png)
![Screenshot books](images/image%2021.png)
**Soal 9**
![Screenshot books](images/asynchronous5.gif)

Langkah 4: Tambah method handleError()

Menambahkan kode di dalam class \_FutureStatePage
![Screenshot books](images/image%2022.png)

**Soal 10**

Panggil method handleError() tersebut di ElevatedButton, lalu run. Apa hasilnya? Jelaskan perbedaan kode langkah 1 dan 4!

- Hasilnya adalah setelah 2 detik maka akan muncul **Something terrible happened!**
- Langkah 1: returnError

Simpel dan hanya mensimulasikan error tanpa menangani apa pun dan membutuhkan error handling tambahan oleh pemanggil fungsi.

- Langkah 4: handleError

Menggabungkan pemanggilan fungsi returnError dengan logika error handling dan eksekusi akhir. Lebih lengkap dan siap pakai, terutama untuk memperbarui UI berdasarkan hasil eksekusi fungsi.

**Praktikum 6: Menggunakan Future dengan StatefulWidget**

Langkah 1: install plugin geolocator
![Screenshot books](images/image%2023.png)

Langkah 2: Tambah permission GPS
![Screenshot books](images/image%2024.png)

Langkah 3: Buat file geolocation.dart

![Screenshot books](images/image%2025.png)

Langkah 4: Buat StatefulWidget
![Screenshot books](images/image%2026.png)

Langkah 5: Isi kode geolocation.dart
![Screenshot books](images/image%2027.png)
**Soal 11**
![Screenshot books](images/image%2028.png)

Langkah 6: Edit main.dart
![Screenshot books](images/image%2029.png)

Langkah 7: Run
![Screenshot books](images/image%2030.png)

Langkah 8: Tambahkan animasi loading
![Screenshot books](images/image%2031.png)

**Soal 12**

- Jika Anda tidak melihat animasi loading tampil, kemungkinan itu berjalan sangat cepat. Tambahkan delay pada method getPosition() dengan kode await Future.delayed(const Duration(seconds: 3));
  ![Screenshot books](images/image%2032.png)
- Apakah Anda mendapatkan koordinat GPS ketika run di browser? Mengapa demikian?

  Karena penggunaan Geolocator.requestPermission(); yang akan memunculkan prompt untuk meminta izin dari pengguna untuk memberikan data lokasi pada aplikasi.
  ![Screenshot books](images/asynchronous6.gif)

**Praktikum 7: Manajemen Future dengan FutureBuilder**

Langkah 1: Modifikasi method getPosition()

Mengganti isi method
![Screenshot books](images/image%2033.png)

Langkah 2: Tambah variabel
![Screenshot books](images/image%2034.png)

Langkah 3: Tambah initState()
![Screenshot books](images/image%2035.png)

Langkah 4: Edit method build()
![Screenshot books](images/image%2036.png)

**Soal 13**

- Apakah ada perbedaan UI dengan praktikum sebelumnya? Mengapa demikian?

Ada perbedaan UI dengan praktikum sebelumnya, perbedaan UI terjadi karena pada praktikum sebelumnya pembaruan tampilan dilakukan secara manual menggunakan setState(), sedangkan pada kode dengan FutureBuilder pembaruan UI dikelola secara otomatis berdasarkan status Future (waiting atau done). FutureBuilder membuat kode lebih sederhana, reaktif, dan efisien karena tidak memerlukan variabel tambahan atau logika manual untuk memantau status loading dan hasil data.

- Capture hasil praktikum Anda berupa GIF dan lampirkan di README. Lalu lakukan commit dengan pesan "W11: Soal 13".
  ![Screenshot books](images/asynchronous7.gif)
- Seperti yang Anda lihat, menggunakan FutureBuilder lebih efisien, clean, dan reactive dengan Future bersama UI.

Langkah 5: Tambah handling error

Menambahkan kode untuk menangani ketika terjadi error. Kemudian hot restart.
![Screenshot books](images/image%2040.png)

**Soal 14**

- Apakah ada perbedaan UI dengan langkah sebelumnya? Mengapa demikian?

Ada perbedaan UI dengan langkah sebelumnya, perbedaan UI terjadi karena langkah baru menampilkan data lokasi yang lebih terformat, seperti Latitude dan Longitude, dibandingkan langkah sebelumnya yang hanya menampilkan string saja dari objek Position. Selain itu langkah yang baru menambahkan penanganan error yang lebih informatif dengan pesan kesalahan jika terjadi error.

- Capture hasil praktikum Anda berupa GIF dan lampirkan di README. Lalu lakukan commit dengan pesan "W11: Soal 14".
  ![Screenshot books](images/asynchronous8.gif)

**Praktikum 8: Navigation route dengan Future Function**

Langkah 1: Buat file baru navigation_first.dart
![Screenshot books](images/image%2041.png)

Langkah 2: Isi kode navigation_first.dart
![Screenshot books](images/image%2042.png)

**Soal 15**

- Tambahkan nama panggilan Anda pada tiap properti title sebagai identitas pekerjaan Anda.
  ![Screenshot books](images/image%2050.png)
  ![Screenshot books](images/image%2051.png)
- Silakan ganti dengan warna tema favorit Anda.

Langkah 3: Tambah method di class \_NavigationFirstState
![Screenshot books](images/image%2043.png)

Langkah 4: Buat file baru navigation_second.dart
![Screenshot books](images/image%2044.png)

Langkah 5: Buat class NavigationSecond dengan StatefulWidget
![Screenshot books](images/image%2045.png)

Langkah 6: Edit main.dart

Melakukan edit properti home.
![Screenshot books](images/image%2046.png)

Langkah 8: Run
![Screenshot books](images/image%2047.png)
![Screenshot books](images/image%2048.png)

**Soal 16**

- Cobalah klik setiap button, apa yang terjadi ? Mengapa demikian ?

  Jika klik setiap button, maka **Navigation First Screen** akan berubah sesuai warna yang dipilih. Karena ketika tombol di **Navigation Second Screen** ditekan, warna yang dipilih dikembalikan ke **Navigation First Screen** melalui Navigator.pop, lalu fungsi \_navigateAndColor menangkap warna tersebut, memperbarui properti latar belakang, dan akan ada pembaruan UI dengan setState, sehingga background **Navigation First Screen** berubah sesuai tombol warna yang dipilih.
- Gantilah 3 warna pada langkah 5 dengan warna favorit Anda!
  ![Screenshot books](images/image%2049.png)
- Capture hasil praktikum Anda berupa GIF dan lampirkan di README. Lalu lakukan commit dengan pesan "W11: Soal 16".
  ![Screenshot books](images/asynchronous9.gif)

**Praktikum 9: Memanfaatkan async/await dengan Widget Dialog**

Langkah 1: Buat file baru navigation_dialog.dart
![Screenshot books](images/image%2052.png)

Langkah 2: Isi kode navigation_dialog.dart
![Screenshot books](images/image%2053.png)

Langkah 3: Tambah method async
![Screenshot books](images/image%2054.png)

Langkah 4: Panggil method di ElevatedButton
![Screenshot books](images/image%2055.png)

Langkah 5: Edit main.dart

Mengubah properti home
![Screenshot books](images/image%2056.png)

Langkah 6: Run
![Screenshot books](images/image%2057.png)

**Soal 17**

- Cobalah klik setiap button, apa yang terjadi ? Mengapa demikian ?

Jika klik setiap button, maka **Navigation Dialog Screen** akan berubah sesuai warna yang dipilih. Karena ketika tombol di **Very important question** ditekan, warna yang dipilih dikembalikan ke **Navigation Dialog Screen** melalui Navigator.pop, lalu fungsi \_navigateAndColor menangkap warna tersebut, memperbarui properti latar belakang, dan akan ada pembaruan UI dengan setState, sehingga background **Navigation Dialog Screen** berubah sesuai tombol warna yang dipilih.
- Gantilah 3 warna pada langkah 3 dengan warna favorit Anda!
- Capture hasil praktikum Anda berupa GIF dan lampirkan di README. Lalu lakukan commit dengan pesan "W11: Soal 17".
