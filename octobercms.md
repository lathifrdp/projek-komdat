<h1 align="center"><img src="https://avatars0.githubusercontent.com/u/5554805?s=400&v=4"></h1>

# October
**October** adalah suatu *Content Management System* (CMS) yang gratis dan *open source* yang berbasis [Laravel PHP Framework](https://laravel.com/). October dibangun oleh [Alexey Bobkov](https://www.linkedin.com/in/aleksey-bobkov-232ba02b) dan [Samuel Georges](https://www.linkedin.com/in/samuel-georges-0a964131) yang merupakan programmer dan UX Design dari Kanada dan Australia. October dirilis pada 15 Mei 2014. October dibuat bertujuan untuk mempermudah user dalam membangun sebuah website.

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
    
5. Setelah ssh sudah terinstall, akses ubuntu server dengan [PuTTY](http://www.putty.org/).
 
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
1. Instal [composer](https://getcomposer.org/download/) yang digunakan untuk mengarahkan aplikasi october ke dalam database yang dibuat
 
    ```
    $ php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    $ php composer-setup.php
    $ php -r "unlink('composer-setup.php');"
    ```

2. Buat database mysql untuk menampung data dari aplikasi october
    ```
    $ mysql -u root
    ```
    
    ```
    > create database databasename
    ```
    
3. Buat *directory* pada `/var/www/html/` untuk menampung *file* October yang akan diinstal
 
    ```
    $ mkdir october
    ```
    
4. Masuk ke *directory* october yang sudah dibuat. Lalu *download* file October dari website [octobercms.com](https://octobercms.com/)

    ```
    $ php -r "eval('?>'.file_get_contents('https://octobercms.com/api/installer'));"
    ```
    
5. Instal october untuk mengarahkan aplikasi october ke database yang telah dibuat

    ```
    $ php artisan october:install
    ```
