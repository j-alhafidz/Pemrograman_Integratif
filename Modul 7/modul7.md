Jundullah Al Hafidz - 215150700111033

### Relasi

Hubungan antar tabel yang dilakukan dengan pencocokan primary key dengan foreign key untuk mengombinasikan data dari satu tabel dengan tabel lainnya.

### Foreign Key

Properti yang digunakan untuk menandai hubungan dua tabel atau lebih. Foreign key pada tabel anak (child) akan menunjuk tabel induk (parent) yang menjadi referensinya (reference).

### One-to-Many

Relasi yang menunjukkan hubungan antar tabel dimana baris pada tabel induk dapat terhubung dengan satu atau lebih baris di tabel anak. Sementara baris pada tabel anak hanya dapat terhubung dengan satu baris di tabel induk.

Contoh penerapan one-to-many

- Satu tutorial dapat memiliki banyak komentar, namun satu komentar hanya dapat berada di satu tutorial
- Satu dosbing dapat memiliki banyak mahasiswa, namun mahasiswa hanya dapat dibimbing satu dosen

### Many-to-Many

Relasi yang menunjukkan hubungan antar tabel dimana baris pada tabel induk dapat terhubung dengan satu atau lebih baris di tabel anak. Berlaku sebaliknya pada tabel anak yang dapat terhubung dengan satu atau lebih baris di tabel induk.

Contoh penerapan many-to-many

- Satu mahasiswa dapat mengambil banyak mata kuliah, namun satu mata kuliah dapat diambil banyak mahasiswa
- Postingan dapat memiliki banyak tag, namun satu tag dapat dimiliki banyak postingan.

Kombinasi baris pada relasi many-to-many diatur dengan junction table.

### Junction Table

Tabel yang digunakan untuk mengatur kombinasi baris pada relasi many-to-many. Junction table berisi foreign key dari kedua tabel yang memiliki relasi many-to-many.

## 📒Langkah Percobaan

### Pembuatan Tabel

Berikut ini tabel yang akan digunakan pada praktikum kali ini
posts | comments | tags | post_tag |
--- | --- | --- | --- |
id | id | id | postId |
content (STRING) | review (STRING) | name | tagId |

1. Memastikan server database aktif dan membuat database dengan nama `lumenapi`<br>
   ![Memastikan server database dan nama database](screenshot/pic1.png) <br><br>
2. Mengubah konfigurasi database pada file `.env` <br>
   ![Mengkonfigurasi env](screenshot/pic2.png) <br><br>
3. Menghidupkan library bawaan lumen dengan membuka file `app.php` pada folder `boostrapt` <br>
   ![Mengaktifkan library lumen](screenshot/pic3.png)
4. Menjalankan Command untuk membuat file migration
   ![Membuat file migration](screenshot/pic4.png)
5. Mengubah fungsi `up()` pada file `create_post_table`
6. Mengubah fungsi `up()` pada file `create_comment_table`
7. Mengubah fungsi `up()` pada file `create_tags_table`
8. Mengubah fungsi `up()` pada file `create_post_tag_table`
   ![Mengubah fungsi up() file create_post_table](screenshot/pic5.png)
10. Menjalankan command `php artisan migrate`
   ![Menjalankan command](screenshot/pic6.png)

### Pembuatan Model

1. Membuat file dengan nama `Post.php` dan mengisi dengan baris kode berikut <br>
   ![Membuat HomeController](screenshot/pic7.png)
2. Membuat file dengan nama `Comment.php` dan mengisi dengan baris kode berikut <br>
   ![Mengedit route /](screenshot/pic8.png)
3. Membuat file dengan nama `Tag.php` dan mengisi dengan baris kode berikut <br>
   ![Menjalankan aplikasi](screenshot/pic9.png)

### Relasi One-to-Many

1. Tambahkan fungsi `comments()` pada file Post.php<br>
   ![Menambahkan fungsi comment() pada file Post.php](screenshot/pic10.png)
2. Tambahkan fungsi `post()` dan atribut postId pada `$fillable` pada file `Comment.php`<br>
   ![Menambahkan fungsi post() pada file Comment.php](screenshot/pic11.png)
3. Membuat file `PostController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat file PostController.php](screenshot/pic12.png)
4. Membuat file `CommentController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat file CommentController.php](screenshot/pic13.png)
5. Tambahkan baris berikut pada `routes/web.php` <br>
   ![Menambahkan baris pada routes/web.php](screenshot/pic14.png)
6. Membuat satu post menggunakan Postman <br>
   ![Membuat satu post](screenshot/pic15.png)
7. Membuat satu comment menggunakan Postman <br>
   ![Membuat satu comment](screenshot/pic16.png)
8. Menampilkan post menggunakan Postman <br>
   ![Menampilkan post](screenshot/pic17.png)

### Relasi Many to Many

1. Menambahkan fungsi `tags()` pada file Post.php<br>
   ![Menambahkan fungsi tags() pada file Post.php](screenshot/pic18.png)
2. Menambahkan fungsi `posts()` pada file Tag.php<br>
   ![Menambahkan fungsi posts() pada file Tag.php](screenshot/pic19.png)
3. Membuat file `TagController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat file TagController.php](screenshot/pic20.png)
4. Menambahkan fungsi `addTag` dan response tags pada `PostController.php` <br>
   ![Menambahkan fungsi addTag() pada PostController.php](screenshot/pic21.png)
5. Menambahkan baris berikut pada `routes/web.php` <br>
   ![Menambahkan baris pada routes/web.php](screenshot/pic22.png)
6. Membuat satu tag menggunakan Postman <br>
   ![Membuat satu tag](screenshot/pic23.png)
7. Menambahkan tag `jadul` pada post `disana engkau berdua` <br>
   ![Menambahkan tag jadul pada post disana engkau berada](screenshot/pic24.png)
8. Menampilkan post `disana engkau berdua`” menggunakan Postman <br>
   ![Menampilkan post disana engkau berada](screenshot/pic25.png)
9. Membuat postingan `tanpamu apa artinya` menggunakan Postman <br>
   ![Membuat post tanpamu apa artinya](screenshot/pic26.png)
10. Menambahkan tag `jadul` pada postingan `tanpamu apa artinya` <br>
    ![Menambahkan tag jadul pada post tanpamu ada artinya](screenshot/pic27.png)
11. Membuat tag `lagu` menggunakan Postman <br>
    ![Membuat tag lagu](screenshot/pic28.png)
12. Menambahkan tag `lagu` pada postingan `tanpamu apa artinya` <br>
    ![Menambahkan tag lagu pada post tanpamu aapa artinya](screenshot/pic29.png)
13. Menampilkan post pertama <br>
    ![Menampilkan post pertama](screenshot/pic30.png)
14. Menampilkan post kedua <br>
    ![Menampilkan post kedua](screenshot/pic31.png)
