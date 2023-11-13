# Instalasi Apache, Wordpress, Nginx, dan Tableau Desktop
# Panduan Cara Menginstall Apache, Wordpress, Nginx dan Tableu Desktop dengan Ubuntu Server

Laporan ini memberikan langkah-langkah cara mengistall Apache, Wordpress dan sebagai dalam lingkungan Ubuntu Server Versi 22.04

# Daftar Isi
 - [Cara Menginstall Apache2 dan Cara Remote Server]
 - [Cara Menginstall Wordpress]
 - [Cara Menginstall Nginx]
 - [Cara Menginstall Tableau Desktop Dari Windows]

# Cara Menginstall Apache2 dan Cara Remote Server
## Proses Instalasi Apache
Sebelum masuk kelangkah-langkah pastikan sebelum sudah menginstal Ubuntu Server, lalu jalankan
   1. Sebelum menginstall, update terlebih dahulu sistem Ubuntu Server dengan perintah
     
      ```
      sudo apt update
      ```
   2. Selanjutnya, install Apache2 dengan cara memasukkan perintah berikut
     
      ```
      sudo apt install apache2
      ```
   3. Kemudian lakukan pengecekan apakah apache2 sudah terinstall dengan baik

      ```
      sudo ufw app list
      ```
   4. Langkah berikutnya cek status dari Apache2

      ``` 
      sudo systemctl status apache2
      ```
   5. Selanjutnya langkah terakhir pengecekan apache diweb browser apakah apache2 sudah bekerja diubuntu server anda
     
      ![Web Apache2](https://github.com/FakhriNaufal25/Apache-Wordpress-Nginx-Tableau-Desktop/blob/main/Apache%20Web.png)
      Untuk melihat ip address dari ubuntu anda ketikan perintah ini `ifconfig` atau `hostname -I`


## Proses Instalasi OpenSSH dan Remote Server 
   1. Install OpenSSH di Ubuntu Server menggunakan perintah berikut
      
      ```
      sudo apt install ssh
      ```
   2. Kemudian untuk mengecek tools ssh sudah terinstal dengan perintah berikut

      ```
      sudo ufw app list
      sudo ufw allow OpenSSH
      ```
   3. Selanjutnya cara menggunakan remote server cmd, cek ip Ubuntu Server dengan cara `ifconfig` lalu ketikkan
      
      ```bash
      SSH 'username ubuntu server'@'localhost'
      ```
      Contohnya
      
      ```
      SSH Budi@10.9.52.168
      ```

## Proses Instalasi Putty dan Remote Server
   1. Install aplikasi PuTTY diwindows masing-masing. disini kita install PuTTY yang MSI(for windows) yang 64-bit x86, download sampai selesai
   2. Buka aplikasi PuTTY yang sudah terinstall tadi lalu masukkan ip Ubuntu Server dengan perintah `ifconfig`
   3. Login kedalam PuTTY menggunakan username dan password yang sudah didaftarkan saat penginstallan Ubuntu Server

# Cara Menginstall Wordpress
## Instalasi Tumpukan Lamp
Tumpukan lamp ialah Linux, Apache, MySQL, PHP. Tools berikut digunakan untuk pendukung wordpress
## Proses Instalasi MySQL Server
   1. Langkah pertama, Instalasi MySQL server

      ```
      sudo apt install mysql-server
      ```
   2. Selanjutnya, install tools keamanan untuk MySQL anda

      ```
      sudo mysql_secure_installation
      ```
      Klik `y` sampai hasil akhir `all done`
      
## Proses Instalasi PHP
WordPress adalah CMS berbasis PHP. PHP diperlukan untuk memproses konten dinamis di situs WordPress.
   1. Instalasi PHP
      
      ```
      sudo apt install php libapache2-mod-php php-mysql
      ```
      
   2. Instalasi Ekstensi PHP yang Dibutuhkan untuk WordPress

      ```
      sudo apt install php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip
      ```
   3. Mengecek Versi PHP

      ```
      php -v
      ```
Setelah instalasi ekstensi PHP, restart Apache dengan perintah berikut `sudo systemctl restart apache2`

## Proses Instalasi Wordpress
   1. Sebelum menginstal wordpress, masuklah ke direktori `/var/www/html`
   2. Install wordpress versi terbaru

      ```
      sudo wget -c http://wordpress.org/latest.tar.gz
      ```
   3. Ekstrak File dan Lakukan Pengecekan dengan perintah berikut

      ```
      sudo tar -xzvf latest.tar.gz
      ls -l
      ```
   4. Membuat Database untuk WordPress

      ```
      sudo mysql -u root -p
      ```
      Lalu buatlah sebuah database, sebagai contoh
      
      ```sql
      CREATE DATABASE fakhri_db;
      CREATE USER fakhri_user@localhost IDENTIFIED BY 'password';
      GRANT ALL PRIVILEGES ON fakhri_db.* TO fakhri_user@localhost;
      FLUSH PRIVILEGES;
      exit;
      ```
   5. Beri akses untuk dapat dieksekusi ke folder WordPress
      
      ```
      sudo chmod -R 777 wordpress
      ```
   6. Lakukan konfigurasikan pada wordPress
      
      ```
      cd wordpress/
      mv wp-config-sample.php wp-config.php
      nano wp-config.php
      ```
      Ubahlah pada baris `define( 'DB_NAME', 'Nama Database' );` dan diganti sampai kebawah sesuai perintahnya, lalu simpan file `CTRL + X`
   7. Selanjunya akses halaman wordpress pada web
      
      ```
      https://localhost/wordpress/
      ```
      Jika sudah keluar tampilan seperti ini maka intalasi wordpress berhasil
      ![Wordpress Home]


## Cara Menginstall Nginx
   1. Langkah pertama perbarui sistem server ubuntu server dengan perintah `sudo apt update`
   2. Selanjutnya install Nginx dan periksa versi nginx

      ```
      sudo apt install nginx
      nginx -v
      ```
   3. Periksa status Nginx

      ```
      sudo systemctl status nginx
      ```
      Jika aktif Nginx bisa lansung digunakan jika tidak aktif, apache2 yang sudah diinstall tadi harus dinon-aktifkan terlebih dengan cara

      ```
      sudo systemctl disable apache2
      sudo systemctl restart nginx
      ```
   4. Salanjutnya periksa nginx menggunakan web browser
     
      ```bash
      https://'ip address anda'/index.nginx-debian.html/
      ```
      ![Nginx]
## Cara Menginstall Tableau Desktop Dari Windows
   1. Carilah Tableau dikolom pencarian web browser anda
   2. Lakukan pembuatan akun untuk tableau desktop
   3. Kemudian, unduh tableau desktop untuk windows
   4. Buka file unduhan dan instal aplikasi seperti biasa
      ![Tableau]














 








 
    

