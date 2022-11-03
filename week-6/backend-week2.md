# **Writing Week 6 (Backend Week 2)**
## **MySQL Basic**
### **Database**
<div align='justify'>sebuah set data yang tersimpan di dalam sebuah komputer. Data tersebut biasanya memiliki struktur agar data dapat mudah di akses dan diolah. serta tempat untuk menyimpan data koleksi yang terstruktur didalamnya terdapat informasi dan data bersifat elektronik, salah satu cara mengkoneksikannya dengan DBMS (database management system) yang berbasis SQL (structured query language) dalam penulisan dan pembuatan query data. 

**DBMS**, sistem penorganisasian dan sistem pengolahan Database pada komputer. DBMS atau database management system ini merupakan perangkat lunak (software) yang dipakai untuk membangun basis data yang berbasis komputerisasi.

### **Relational Database**
<div align='justify'> kumpulan item data yang saling terhubung dan relasi atau hubungannya telah ditentukan sebelumnya. disusun dalam set tabel dengan kolom dan baris. sebuah tabel memiliki relasi dan hubungan dengan tabel lain begitupun sebaliknya.

- **ciri-ciri** :
    - Semua entry / elemen data pada suatu baris dan kolom tertentu harus mempunyai nilai tunggal (single value)
    - suatu nilai yang tidak dapat dibagi lagi (atomic value), 
    - bukan suatu kelompok pengulangan, dll

- **Tujuan**, menyediakan metode deklaratif untuk menspesifikasikan data dan kueri: pengguna secara langsung menyatakan bahwa informasi dari database mengandung informasi apa dan informasi yang diinginkan, serta membiarkan sistem software manajemen database mengatur struktur data

- **RDBMS**, SQL server adalah sistem manajemen database relasional atau disingkat RDBMS besutan Microsofft. Mirip dengan produk pasaran RDBMS lainnya, SQL server ini dibangun di atas SQL yakni, bahasa pemrograman standar untuk berinteraksi dengan database relasional. Cara Kerja RDBMS : 
    - Setiap sistem akan memiliki jumlah tabel yang berbeda-beda dengan setiap tabel memiliki unique primary key (kunci primer) yang unik. Lalu, kunci utama tersebut kemudian digunakan untuk mengidentifikasi setiap tabel yang ada.


### **MySQL**
<div align='justify'> Adalah sistem manajemen database relasional (Relational Database Management System) yang merupakan turunan salah satu konsep utama dalam querying database yaitu SQL, selain MySQL juga ada : PostgreSQL, MariaDB, oracle, dll. Keistimewaan MySQL :

- Dapat Digunakan banyak user, MySQL dapat digunakan oleh beberapa pengguna dalam waktu yang bersamaan tanpa mengalami masalah / konflik.
- Compatible dan portabilitasnya, MySQL dapat berjalan stabil pada berbagai sistem operasi seperti Windows, Linux, MacOS dll

### **Tipe Data MySQL**
- **Number**, Kumpulan karakter angka
    - **Int**, Angka bulat seperti 1, 22, 1009, dll. memiliki range dari `-2,147,483,648` sampai `2,147,483,647`.
    - **Float**, Angka yang menggunakan koma, namun penulisannya dalam dokumentasi menjadi titik (.), seperti : 3.14, 90.78, dll. memiliki range dari `-3.402823466E+38` sampai `3.402823466E+38`
    - **Decimal**, angka pecahan, jumlah angka pecahan dibelakang koma sudah di setting atau ditentukan dari awal misal 2 angka, dll. range decimal (4,1) total 4 angka dengan 1 angka dibelakang koma `-999,9` sampai `999,9`. range decimal (3,2) total 3 angka dengan 2 angka dibelakang koma `-9,99` sampai `9,99`. range decimal (6,2) total 6 angka dengan 2 angka dibelakang koma `-9999,99` sampai `9999,99`
- **String**, kumpulan karakter juga simbol karakter
    - **Char**, tipe data string dengan panjang karakter yang sudah ditentukan serta memorinya sesuai panjang karakter yang sudah didefinisikan, biasanya dipakai disuatu kode campuran angka dan karakter, contoh : `char(5)` => `LM-01`
    - **Varchar**, Tipe data string dengan panjang karakter dan memorinya yang fleksibel tersebut maksimal 255, `varchar(255)`, `varchar(50)`, dll. contoh `varchar(20)` => `Jasmine Hertiana`
    - **Text**, Tipe data string dengan penyimpanan yang lebih panjang dari varchar, dalam dokumentasinya tidak perlu ditentukan panjang karakternya cukup `text`
    - **Enum**, tipe data string yang khusus untuk kolom yang memiliki nilai data yang sudah ditentukan. contoh : `enum('Pria', 'Wanita')`, data yang akan tersimpan merupakan salah satu dari nilai yang sudah ditentukan tersebut misal `Wanita`.
- **Boolean**, 2 tipe data yaitu `TRUE` dan `FALSE`, dan konversi integer atau int nya dengan representasi `TRUE = 1`, dan `FALSE = 0`. Biasanya digunakan setelah ada eksekusi perbandingan
- **Date Time**, tipe data yang menyimpan format tanggal dan waktu
    - **DATE**, menyimpan tanggal. Format : `YYYY-MM-DD` => `2003-03-24` yang artinya tanggal 24 bulan Maret tahun 2003
    - **DATETIME**, menyimpan tanggal dan waktu. Format : `YYYY-MM-DD hh:mm:ss` => `2003-03-24 17:30:50` yang artinya tanggal 24 bulan Maret tahun 2003 pukul 17 sore menit 30 detik 50
    - **TIME**, menyimpan waktu. Format : `hh:mm:ss` => `17:30:50` yang artinya pukul 17 sore menit 30 detik 50
    - **timestamp**, menyimpan tanggal dan waktu dan juga UTC nya atau timezone. format : `CCYY-MM-DD hh:mm:ss +00:00`
- **Default**, tipe data yang telah di set atau ditentukan dan diatur untuk nilai defaultnya jika tidak diisi dengan nilai `DEFAULT("Bonjour")`
- **Null**, tipe data yang tidak memiliki isi maupun kosong dan tidak memiliki nilai atau data `NULL`

### **Query MySQL Basic**

- **Primary Key**, seperti namanya primary key sebagai dasar identifikasi untuk membedakan suatu baris/record dengan baris/record lainnya dalam suatu tabel. oleh karena itu primary key bersifat unik, dan setiap tabel hanya boleh memiliki 1 kolom/atribut/field yang merupakan primary key
- **Foreign Key** adanya foreign key membuktikan bahwa sebuah database tersebut memiliki pengolahan RDBMS. Foreign key adalah suatu atribut/kolom/field yang direferensikan dari primary key suatu atribut/kolom/field pada tabel lain untuk menciptakan hubungan/relasi antara dua tabel.

#### **DDL (Data Definition Language)**
- **membuat database baru**
    ```
    mysql> CREATE DATABASE peminjaman;
    Query OK, 1 row affected (0.19 sec)
    ```

- **melihat database yang ada**
    ```
    mysql> SHOW DATABASES;
    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | mysql              |
    | peminjaman         |
    | performance_schema |
    | perpustakaan       |
    | sakila             |
    | sys                |
    | world              |
    +--------------------+
    7 rows in set (0.00 sec)
    ```

- **menggunakan database yang sudah ada**
    ```
    mysql> USE peminjaman
    Database changed
    mysql>
    ```

- **menghapus / menghilangkan database yang dipilih dari MySQL**
    ```
    mysql> DROP DATABASE perpustakaan;
    Query OK, 0 rows affected (0.12 sec)

    mysql> SHOW DATABASES;
    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | mysql              |
    | peminjaman         |
    | performance_schema |
    | sakila             |
    | sys                |
    | world              |
    +--------------------+
    7 rows in set (0.04 sec)
    ```

- **membuat table baru** pada database peminjaman
    ```
    mysql> CREATE TABLE peminjaman_perpustakaan (
        -> id INT(5) AUTO_INCREMENT PRIMARY KEY,
        -> nama_anggota VARCHAR(50) NOT NULL,
        -> tanggal_pinjam DATE NOT NULL,
        -> nama_pengurus VARCHAR(50),
        -> judul_buku VARCHAR(20) NOT NULL,
        -> kode_buku CHAR(5));
    Query OK, 0 rows affected, 1 warning (0.29 sec)
    ```

- **melihat semua table di database peminjaman**
    ```
    mysql> SHOW TABLES;
    +-------------------------+
    | Tables_in_peminjaman    |
    +-------------------------+
    | denda                   |
    | peminjaman_perpustakaan |
    +-------------------------+
    2 rows in set (0.11 sec)
    ```

- **menghapus Tabel**
    ```
    mysql> DROP TABLES denda;
    Query OK, 0 rows affected (0.17 sec)

    mysql> SHOW TABLES;
    +-------------------------+
    | Tables_in_peminjaman    |
    +-------------------------+
    | peminjaman_perpustakaan |
    +-------------------------+
    1 row in set (0.00 sec)
    ```

- **manipulasi kolom di table yang dipilih**
    ```
    mysql> ALTER TABLE peminjaman_perpustakaan
        -> ADD alamat_anggota VARCHAR(255);
    Query OK, 0 rows affected (0.23 sec)
    Records: 0  Duplicates: 0  Warnings: 0

    mysql> ALTER TABLE peminjaman_perpustakaan
        -> DROP COLUMN kode_buku;
    Query OK, 0 rows affected (0.07 sec)
    Records: 0  Duplicates: 0  Warnings: 0
    ```

#### **DML (Data Manipulation Language)**
- **menambah data/record**
    ```
    mysql> INSERT INTO peminjaman_perpustakaan
        -> (id, nama_anggota, tanggal_pinjam, nama_pengurus, judul_buku, alamat_anggota)
        -> VALUES
        -> (1, 'jasmine', '2022-03-03', 'haqi', 'kalkulus', 'Bekasi'),
        -> (2, 'mine', '2022-05-03', 'abay', 'accurate', 'Tambun'),
        -> (3, 'yasmin', '2022-05-12', 'ghani', 'accounting', 'Mekarsari');
    Query OK, 3 rows affected (0.03 sec)
    Records: 3  Duplicates: 0  Warnings: 0
    ```
- **melihat isi seluruh data di table yang dipilih**
    ```
    mysql> SELECT * FROM peminjaman_perpustakaan;
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  1 | jasmine      | 2022-03-03     | haqi          | kalkulus   | Bekasi         |
    |  2 | mine         | 2022-05-03     | abay          | accurate   | Tambun         |
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    +----+--------------+----------------+---------------+------------+----------------+
    3 rows in set (0.00 sec)
    ```

- **melihat isi data tertentu di table yang dipilih**
    ```
    mysql> SELECT id, nama_anggota, tanggal_pinjam FROM peminjaman_perpustakaan;
    +----+--------------+----------------+
    | id | nama_anggota | tanggal_pinjam |
    +----+--------------+----------------+
    |  1 | jasmine      | 2022-03-03     |
    |  2 | mine         | 2022-05-03     |
    |  3 | yasmin       | 2022-05-12     |
    +----+--------------+----------------+
    3 rows in set (0.00 sec)
    ```

- **melihat isi data tertentu di table yang dipilih menggunakan alias / AS untuk mengubah nama kolom**
    ```
    mysql> SELECT judul_buku AS "Sedang Dipinjam" FROM peminjaman_perpustakaan;
    +-----------------+
    | Sedang Dipinjam |
    +-----------------+
    | kalkulus        |
    | accurate        |
    | accounting      |
    +-----------------+
    3 rows in set (0.00 sec)
    ```

- **melihat isi data tertentu di table yang dipilih dengan pengkondisian**
    ```
    mysql> SELECT * FROM peminjaman_perpustakaan WHERE id = 3;
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    +----+--------------+----------------+---------------+------------+----------------+
    1 row in set (0.00 sec)

    mysql> SELECT * FROM peminjaman_perpustakaan WHERE id IN (2,3);
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  2 | mine         | 2022-05-03     | abay          | accurate   | Tambun         |
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    +----+--------------+----------------+---------------+------------+----------------+
    2 rows in set (0.03 sec)

    mysql> SELECT * FROM peminjaman_perpustakaan WHERE id = 3 AND nama_pengurus = 'ghani';
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    +----+--------------+----------------+---------------+------------+----------------+
    1 row in set (0.00 sec)

    mysql> SELECT * FROM peminjaman_perpustakaan WHERE id = 3 OR nama_pengurus = 'haqi';
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  1 | jasmine      | 2022-03-03     | haqi          | kalkulus   | Bekasi         |
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    +----+--------------+----------------+---------------+------------+----------------+
    2 rows in set (0.00 sec)

    mysql> SELECT * FROM peminjaman_perpustakaan WHERE NOT alamat_anggota = 'Bekasi';
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  2 | mine         | 2022-05-03     | abay          | accurate   | Tambun         |
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    +----+--------------+----------------+---------------+------------+----------------+
    2 rows in set (0.00 sec)

    mysql> SELECT * FROM peminjaman_perpustakaan WHERE NOT alamat_anggota = 'Bekasi'
        -> ORDER BY tanggal_pinjam DESC;
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    |  2 | mine         | 2022-05-03     | abay          | accurate   | Tambun         |
    +----+--------------+----------------+---------------+------------+----------------+
    2 rows in set (0.00 sec)
    ```

- **melakukan perbaruan data/record**
    ```
    mysql> UPDATE peminjaman_perpustakaan SET judul_buku = 'python programs' WHERE nama_anggota = 'mine';
    Query OK, 1 row affected (0.07 sec)
    Rows matched: 1  Changed: 1  Warnings: 0

    mysql> SELECT * FROM peminjaman_perpustakaan WHERE nama_anggota = 'mine';
    +----+--------------+----------------+---------------+-----------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku      | alamat_anggota |
    +----+--------------+----------------+---------------+-----------------+----------------+
    |  2 | mine         | 2022-05-03     | abay          | python programs | Tambun         |
    +----+--------------+----------------+---------------+-----------------+----------------+
    1 row in set (0.00 sec)
    ```

- **melakukan penghapusan data**, menggunakan WHERE agar tidak terhapus semua data
    ```
    mysql> DELETE FROM peminjaman_perpustakaan WHERE nama_anggota = 'mine';
    Query OK, 1 row affected (0.07 sec)

    mysql> SELECT * FROM peminjaman_perpustakaan;
    +----+--------------+----------------+---------------+------------+----------------+
    | id | nama_anggota | tanggal_pinjam | nama_pengurus | judul_buku | alamat_anggota |
    +----+--------------+----------------+---------------+------------+----------------+
    |  1 | jasmine      | 2022-03-03     | haqi          | kalkulus   | Bekasi         |
    |  3 | yasmin       | 2022-05-12     | ghani         | accounting | Mekarsari      |
    +----+--------------+----------------+---------------+------------+----------------+
    2 rows in set (0.00 sec)
    ```



