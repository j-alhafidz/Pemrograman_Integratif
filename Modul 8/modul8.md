Jundullah Al Hafidz - 215150700111033

### Authentication

<p align="justify">
Otentifikasi adalah proses untuk mengenali identitas dengan mekanisme pengasosiasian permintaan yang masuk dengan satu set kredensial pengidentifikasi. Kredensial yang diberikan akan dibandingkan dengan database informasi pengguna yang berwenang di dalam sistem operasi lokal atau server otentifikasi.
</p>

### Token

<p align="justify">
Token merupakan nilai yang digunakan untuk mendapatkan akses ke sumber daya yang dibatasi secara elektronik. Penggunaan token ditujukan pada web service yang tidak menyimpan state yang berkaitan dengan penggunaan aplikasi (stateless) seperti session.
</p>

### Authorization

<p align="justify">
Authorization merupakan proses pemberian hak istimewa yang dilakukan setelah proses authentication. Setelah pengguna diidentifikasi pada proses authentication, authorization akan memberikan hak istimewa dan tindakan yang diizinkan kepada pengguna yang ditentukan.
</p>

## Langkah Percobaan

### Register

1. Memastikan terdapat tabel users yang dibuat menggunakan migration pada Bab 3 Basic Routing dan Migration. Berikut informasi kolom yang harus ada <br>
   ![Struktur Tabel User](screenshot/pic1.png)
2. Memastikan terdapat model User.php yang digunakan pada Bab 5 Model, Controller dan Request-Response Handler. Berikut baris kode yang harus ada <br>
   ![User.php](screenshot/pic2.png)
3. Membuat file `AuthController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat AuthController](screenshot/pic3.png)
4. Menambahkan route `auth/register` pada routes/web.php <br>
   ![Menambahkan route auth/register](screenshot/pic4.png)
5. Menjalankan aplikasi pada endpoint `/auth/register` beserta body data username, email, dan password  
   ![Menjalankan aplikasi /auth/register](screenshot/pic5.png)

### Authentication

1. Membuat fungsi `login()` pada file `AuthController.php` <br>
   ![Membuat fungsi login](screenshot/pic6.png)
2. Menambahkan route `auth/login` pada routes/web.php <br>
   ![Menambahkan route /auth/login](screenshot/pic7.png)
3. Menjalankan aplikasi pada endpoint `/auth/login` dengan body berikut <br>
   ![Menjalankan aplikasi /auth/login](screenshot/pic8.png)

### Token

1. Menjalankan perintah berikut untuk membuat migrasi baru<br>
   ![Membuat migrasi](screenshot/pic9.png)
2. Menambahkan baris berikut pada migration yang baru terbuat<br>
   ![Mengedit migration token](screenshot/pic10.png)
3. Menambahkan atribut token di `$fillable` pada `User.php` <br>
   ![Menambahkan token pada $fillable](screenshot/pic11.png)
4. Menambahkan baris untuk menambahkan token pada file `AuthController.php` <br>
   ![Menambahkan token pada login](screenshot/pic12.png)
5. Menjalankan perintah `php artisan migrate` untuk menjalankan migrasi terbaru <br>
   ![Menjalankan migrasi terbaru](screenshot/pic13.png)
6. Menjalankan aplikasi pada endpoint `/auth/login` dengan body berikut. Salinlah token yang didapat ke notepad <br>
   ![Menjalankan aplikasi endpoint /auth/login](screenshot/pic14.png)

### Authorization

1. Membuat file `Authorization.php` pada folder `App/Http/Middleware` dan isilah dengan baris berikut<br>
   ![Membuat Authorization](screenshot/pic15.png)
2. Menambahkan middleware yang baru dibuat pada `bootstrap/app.php`<br>
   ![Menambahkan middleware pada boostrapt/app](screenshot/pic16.png)
3. Membuat fungsi `home()` pada `HomeController.php` <br>
   ![Membuat fungsi home pada HomeController](screenshot/pic17.png)
4. Menambahkan route `home` pada `route/web.php` <br>
   ![Menambahkan route home](screenshot/pic18.png)
5. Menjalankan aplikasi pada endpoint `/home` dengan melampirkan nilai token yang didapat setelah login pada header <br>
   ![Menjalankan aplikasi endpoint /home](screenshot/pic19.png)
