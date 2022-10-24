# **Writing Week 5**
## **Web Server dan RESTful API**

### **Komponen Web Server**
<div align="justify">

- **Hardware**, web server sebagai computer yang menyimpan dan mengumpulkan software web server dan file komponen website (HTML, gambar, CSS, dan file JavaScript) yang terkoneksi internet dan mendukung data fisik dan perangkat lain terkoneksi web
- **Software**, web server termasuk beberapa bagian yang mengontrol bagaimana pengguna web mengakses hosted file. dengan menggunakan HTTP Server.

### **Perbedaan Static Web Server dan Dynamic Web Server**

- **Static Web Server**, merujuk pada komputer (hardware) dengan HTTP server (software), disebut statis karena server mengirim hosted file tersebut ke browser.
- **Dynamic Web Server**, merujuk pada static web server dengan software lainnya, biasanya sebuah application server dan database. Disebut dinamis karena application server dapat mengupdate hosted file sebelum mengirim konten ke browser dengan HTTP server.

### **Client-Side dan Server-Side**

- **Client-side**, dari sisi user yang menggunakan browser yang sudah dinamis dan mengirimkan HTTP request ke server agar dapat terproses sebuah aplikasi. Setelah itu, client mendapatkan HTTP response dari request ke server tersebut.
- **Server-side** menerima dan memproses HTTP request dan mengirim HTTP response ke client-side. server-side dapat :

    - mengefisiensi penyimpanan dan mengirim informasi atau konten
    - meningkatkan user experience dengan menyediakan layanan yang memiliki kemudahan 
    - mengontrol akses suatu konten
    - server dapat menyimpan informasi user saat ini dan mengirim response yang berbeda berdasarkan, contohnya fitur histori
    - sebagai fitur notifikasi dan komunikasi live chat. serta membantu data analysis dengan menyediakan data yang diminta.

### **Server-Side Programming**

- **static site**, yang mengembalikan konten hard-coded sama dari server kapanpun sumber data tertentu di request client-side. ketika user ingin menavigasi halaman, browser mengirim HTTP dengan GET request terkait url tsb.
- **Dynamic Site**, dapat mengembalikan data yang berbeda dalam sebuah URL berdasarkan informasi yang tersedia oleh user atau preferensi yang tersimpan dan dapat ditampilan operasi-operasi lain sebagai bagian dari mengembalikan response (contoh : mengirim notifikasi)

### **RESTful API**
<div align="justify">REST adalah singkatan dari Representational State Transfer yang merupakan style arsitektural untuk menyediakan standar diantara sistem komputer di web, mempermudah sistem-sistem untuk komunikasi, standar atau rules dari REST sebagai berikut :

1. uniform interface
2. client-server
3. stateless
4. cacheable
5. layered system
6. code on demand (optional)

code dari sisi client bisa berubah kapan saja tanpa berdampak dengan operasi dalam server, dan code dari sisi server dapat berubah tanpa berdampak dengan operasi dalam client (pemisahan antara front-end dan back-end) yang meruoakan kebalikan dari monolith dimana sisi client dan server tidak dipisah. oleh karena itu sistem monolith, apabila salah satu berubah atau rusak berdampak pada semuanya.
api yang menerapkan standar arsitektur milik REST disebut RESTful API

### **Interaksi antara Client dan Server**
<div align="justify">pada arsitektur REST, client membuat request ke server sebagai permintaan untuk mengambil maupun modifikasi data menjadi langkah awal interaksi. sebuah request terdiri dari :

- ### **HTTP method/verb**
    yang mendefinisikan jenis operasi apa yang ingin digunakan/ditampilkan, terdiri dari :
    
    - GET, mengambil data baik secara spesifik berdasarkan identifier ataupun keseluruhan semua data
    - POST, menambahkan data baru
    - DELETE, menghapus data secara spesifik berdasarkan identifier
    - PUT, mengupdate data secara spesifik berdasarkan identifier, dapat mengedit sebagian ataupun replace secara keseluruhan.
    - PATCH (partial), mengupdate sebagian data secara spesifik berdasarkan identifier

- ### **Header**
    yang dapat digunakan client untuk menyampaikan info mengenai/tentang requestnya. dalam menerima parameter maupun header, contoh :

    ```
    GET /users/20
    Accept: text/html, application/xhtml
    ```

    client mengakses data dengan id 20 pada data users di server dengan mengirim GET request. pada Header fields menyatakan client ingin akan menerima konen dalam bentuk text/html atau application/xhtml


-  ### **Path**
    sebuah path ke sumber data nya, menggunakan endpoint kata benda, contoh penamaan path

    ```
    collection (plural) mengakses seluruh data
    bentuk : 

    https://skilvulstore.api/customers

    singleton (singular) mengakses data tertentu berdasarkan identifier, bentuk :

    https://skilvulstore.api/customers/{id customer}
    https://skilvulstore.api/customers/20

    apabila lebih dari satu kata gunakan strip ( - ) dan huruf kecil semua

    https://skilvulstore.api/customer-histories
    ```

- **pesan di body mengenai isi data (opsional)**

<div align="justify">setelah client mengirimkan request, server menerima dan memproses request, server mengirim response :

- ### **HTTP Response**
    Contoh bentuk response :

    ```
    GET /users/23 HTTP/1.1
    Accept: text/html, application/xhtml
    ```

    maka server akan mengirimkan conten dengan response header berikut :

    ```
    HTTP/1.1 200 (OK)
    Content-Type: text/html
    ```

    **Response Code** yang ditampilkan secara umum terdiri dari :

    - 200 (OK) => standar response untuk HTTP request yang sukses
    - 201 (CREATED) =>  response sbuah HTP request biasanya POST dimana hasil dari item berhasil dibuat atau ditambahkan
    - 204 (NO CONTENT) => response sbuah HTP request biasanya DELETE dimana hasil dari item berhasil dihapus dan tidak tampil
    - 400 (BAD REQUEST)
    - 403 (FORBIDDEN) => user tidak dapat mengakses walaupun data user terdata, karena adanya authorization
    - 404 (NOT FOUND) => data atau konten tidak ditemukan atau belum ada
    - 500 (INTERNAL SERVICE ERROR)

    pada tipe response 2xx (tandanya suatu request berhasil), pada tipe response 3xx (tandanya suatu request redirecting), pada tipe response 4xx (tandanya suatu request tidak berhasil karena client-side error), pada tipe response 5xx (tandanya suatu request tidak berhasil karena server-side error),

