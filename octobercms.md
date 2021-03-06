<h1 align="center"><img src="https://avatars0.githubusercontent.com/u/5554805?s=400&v=4"></h1>

# Dokumentasi
- [Tentang October](#october)
- [Instalasi](#instalasi)
- [Konfigurasi](#konfigurasi)
- [Cara Pemakaian](#cara-pemakaian)
- [Pembahasan](#pembahasan)
- [Referensi](#referensi)

# October
<justify>**October** adalah suatu *Content Management System* (CMS) yang gratis dan *open source* yang berbasis [Laravel PHP Framework](https://laravel.com/). October dibangun oleh [Alexey Bobkov](https://www.linkedin.com/in/aleksey-bobkov-232ba02b) dan [Samuel Georges](https://www.linkedin.com/in/samuel-georges-0a964131) yang merupakan programmer dan UX Design dari Kanada dan Australia. October dirilis pada 15 Mei 2014. October dibuat bertujuan untuk mempermudah user dalam membangun sebuah website.</justify>
<embed src="https://www.youtube.com/watch?v=XOKCXvxZtRE" autostart="false" height="30" width="144" />
# Instalasi

## Kebutuhan Sistem
- PHP versi 7.0 atau diatasnya
- PDO PHP Extension
- cURL PHP Extension
- OpenSSL PHP Extension
- Mbstring PHP Library
- ZipArchive PHP Library
- GD PHP Library

## Proses Instalasi
### Instalasi Web Server
1. Buat VM Ubuntu 64-bit baru pada VirtualBox.
2. Atur *port-forwarding* pada VM supaya bisa diakses dari luar.
3. Jalankan VM Ubuntu server.
4. Instal ssh pada ubuntu server supaya bisa diakses secara *remote*.

    ```
    $ sudo apt install ssh
    ```
    
5. Setelah ssh sudah terinstall, akses ubuntu server dengan [PuTTY](http://www.putty.org/) (untuk pengguna OS Windows).
 
    <img src="https://s1.postimg.org/83n0xsjzy7/image.png">
    
6. Instal kebutuhan sistem yaitu `Apache`, `PHP`, dan `MySQL`.
 
    ```
    $ sudo apt get update
    $ sudo apt install apache2
    $ sudo apt install mysql-server
    $ sudo apt install php
    $ sudo apt install libapache2-mod-php
    $ sudo apt install php-mysql
    $ sudo apt install php-gd php-mcrypt php-mbstring php-xml php-ssh2 php-zip php-curl
    $ sudo service apache2 restart
    ```
    
### Instalasi October
1. Buat *directory* pada `/var/www/html/` untuk menampung *file* October yang akan diinstal
 
    ```
    $ mkdir october
    ```
    
2. Masuk ke *directory* october yang sudah dibuat. Lalu *download* file October dari website [octobercms.com](https://octobercms.com/)

    ```
    $ php -r "eval('?>'.file_get_contents('https://octobercms.com/api/installer'));"
    ```

8. Cek hasil instalasi pada web browser dengan url `localhost:8888/october`
    
    <img src="https://octobercms.com/storage/app/uploads/public/537/f21/0a5/537f210a56ce6580725366.png">
    
# Konfigurasi
1. Buat database mysql untuk menampung data dari aplikasi october
    ```
    $ mysql -u root
    ```
    
    ```
    > create database databasename
    ```
    
2. Instal [composer](https://getcomposer.org/download/) yang digunakan untuk mengarahkan aplikasi october ke dalam database yang dibuat
 
    ```
    $ php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    $ php composer-setup.php
    $ php -r "unlink('composer-setup.php');"
    ```   
    
3. *Setting* aplikasi untuk mengarahkan october ke database yang telah dibuat

    ```
    $ php artisan october:install
    ```
    
4. Ikuti perintah instalasi october sampai selesai

    <img src="https://s1.postimg.org/1hfoefj04v/image.png">
    <img src="https://s1.postimg.org/1zihh6cban/image.png">

5. Ubah *permission* *directory* aplikasi october
    
    ```
    $ chmod -R 775
    ```

6. Halaman admin dapat diakses dengan url `localhost:8888/october/index.php/backend`

7. Masukkan username dan password yang diisikan pada saat konfigurasi *database*

    <img src="https://s1.postimg.org/198wenqka7/image.png">
    
8. Jika username dan password benar maka akan masuk ke halaman dashboard admin
    
    <img src="https://s19.postimg.org/dw30pk903/image.png">
    
9.  Pada menu Settings, terdapat beberapa konfigurasi yang dapat dilakukan diantaranya mendownload plugin atau tema.

10. Sebagai contoh, kami mendownload tema Vanilla yang digunakan sebagai template blog
    ```
    - Settings->Updates & Plugins
    - Ketikkan rainlab.vanilla
    - Aplikasi akan otomatis mengunduh dan menginstal tema
    ```
    <img src="https://s19.postimg.org/ozi1hfkc3/image.png">
    
11. Untuk mengganti tema dapat dilakukan di `Settings->Front-end theme`. Aktifkan tema yang diinginkan

12. Apabila berhasil maka halaman utama blog akan berubah

    <img src="https://s19.postimg.org/dgrqwo543/image.png">

# Maintenance

- Pada menu Settings, kita dapat mengatur apakah akan menyimpan segala aktivitas yang dilakukan ke dalam database, misalnya menyimpan *log bad request* atau *log system events*.
- Untuk mengaktifkannya dapat dilakukan dengan mengklik toggle `on`
    
    <img src="https://s19.postimg.org/3kv9al1ir/image.png">
    
- Untuk aktivitas *log bad request* dapat dilihat pada database di tabel `system_request_logs`
    
    <img src="https://s19.postimg.org/53qnfrq5f/image.png">

# Cara Pemakaian

Octobercms dapat digunakan untuk membuat blog. Blog dapat dibuat di `Blog->New post`. 
Isi konten Blog sesuai dengan yang diinginkan.

<img src="https://s1.postimg.org/1givrbsdbj/image.png">

Setelah isi konten, ditentukan waktu publish dari blog tersebut. Dapat mengupload gambar pada konten ini. Klik Save.

<img src="https://s1.postimg.org/6hnpx1pnen/image.png">

Pergi ke url `localhost:8888/october/index.php/` lalu pilih menu Blog. Pilih Blog yang dibuat untuk melihat hasilnya.

<img src="https://s1.postimg.org/1p2f595o4f/image.png">
<img src="https://s1.postimg.org/2s24g55sbj/image.png">

# Pembahasan

## Kelebihan OctoberCMS
- Akses menu backend cepat karena tidak banyak plugin.
- Front-end nya simpel dan ringan.

## Kekurangan OctoberCMS
- Theme tergolong sedikit.
- Tidak cocok untuk pengguna awam karena butuh skill pemrograman.

## Perbandingan dengan Wordpress

- Untuk installasi, OctoberCMS lebih unggul dibandingkan Wordpress karena OctoberCMS dapat menggunakan CLI atau Wizard. Sedangkan Wordpress hanya dapat menggunakan Wizard.

- Untuk popularitas, OctoberCMS kalah dengan Wordpress dikarenakan Wordpress sudah berdiri lebih dulu (2003) dibandingan OctoberCMS (2014).
    
# Referensi
- https://octobercms.com
- https://github.com/octobercms/october
- https://getcomposer.org/
- https://github.com/auriza/komdat-lab/blob/master/p01.md
- https://leaderinternet.com/blog/october-cms-vs-wordpress
- https://www.codepolitan.com/october-cms-berbasis-laravel-sebuah-opsi-lain-untuk-membangun-website
