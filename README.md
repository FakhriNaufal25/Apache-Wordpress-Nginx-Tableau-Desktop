# Instalasi Apache, Wordpress, Nginx, dan Tableau Desktop
# Panduan Cara Menginstall Apache, Wordpress, Nginx dan Tableu Desktop dengan Ubuntu Server

Laporan ini memberikan langkah-langkah cara mengistall Apache, Wordpress dan sebagai dalam lingkungan Ubuntu Server Versi 22.04

## Daftar Isi
 - [Cara Menginstall Apache2 dan Cara Meremote Server]
 - [Cara Menginstall Wordpress]
 - [Cara Menginstall Nginx]
 - [Cara Menginstall Tableau Desktop Dari Windows]

## Cara Menginstall Apache2 dan Cara Remote Server
# STEP 1 
Sebelum menginstall, update terlebih dahulu sistem Ubuntu Server dengan perintah

    ```bash
    sudo apt update
    ```
# STEP 2
Selanjutnya, install Apache2 dengan cara memasukkan perintah berikut

    ```bash
    sudo apt install apache2
    ```
# STEP 3
Kemudian lakukan pengecekan apakah apache2 sudah terinstall dengan baik

    ```bash
    sudo ufw app list
    ```
    
    jika sudah muncul beberapa list app dan ada apache2 berarti apache2 sudah terinstall
    
# STEP 4 
Langkah berikutnya cek status dari Apache2 

   
    sudo systemctl status apache2
 
# STEP 5
Selanjutnya langkah terakhir pengecekan apache diweb browser apakah apache2 sudah bekerja diubuntu server anda
![Web Apache2](https://github.com/FakhriNaufal25/Apache-Wordpress-Nginx-Tableau-Desktop/blob/main/Apache%20Web.png)
 
    

