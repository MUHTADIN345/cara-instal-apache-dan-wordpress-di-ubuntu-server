# cara instal apache dan wordpress di ubuntu server

Berikut ini merupakan langkah-langkah cara menginstal apache2 dan wordpress

## Table of Contents
- [Install Apache2](#install-apache2)
- [Firewall Configuration](#firewall-configuration)
- [Accessing the Apache2 Web Server in a Browser](#accessing-the-apache2-web-server-in-a-browser)
- [Remote Access to Ubuntu Server](#remote-access-to-ubuntu-server)
- [Install MySQL](#install-mysql)
- [Install PHP](#install-php)
- [Create WordPress Database](#create-wordpress-database)
- [Install WordPress](#install-wordpress)
- [Create WordPress Post](#create-wordpress-post)

## install apache2 di ubuntuserver

1. **Lakukan update erlebih dahulu, jika sudah maka tidak perlu update**
    ```bash
    sudo apt update
    ```
2. **Install Apache2**
    ```bash
    sudo apt install apache2
    ```

## Konfigurasi Firewall

1. **Daftar Aplikasi UFW ketikan perintah**
    ```bash
    sudo ufw app list
    ```

2. **Izinkan Apache Melalui Firewall**
    ```bash
    sudo ufw allow 'Apache'
    ```

3. **Aktifkan UFW**
    ```bash
    sudo ufw enable
    ```

4. **lakukan Periksa Status UFW**
    ```bash
    sudo ufw status
    ```

5. **lalu Periksa Status Apache apakah sudah aktif**
    ```bash
    sudo systemctl status apache2
    ```

## Mengakses Server Web Apache2 di Browser

1. **Periksa Alamat Ip Address pada ubuntu dengan perintah :**
    ```bash
    hostname -I atau ifconfig
    ```

2. **Buka browser**
    kemudian buka browser Anda.

4. **Masukkan Alamat IP**
    Masukkan alamat IP komputer virtual Anda di browser komputer host Anda. Halaman Apache2 default akan muncul.
   
   ![Apache2](https://github.com/MUHTADIN345/cara-instal-apache-dan-wordpress-di-ubuntu-server/assets/126330305/de2b4a51-0450-422c-a565-275f080d7ddd)
   
## Akses dengan Jarak Jauh melalui Server Ubuntu.

### Command Prompt

1. **Buka Command Prompt**
    Buka Command Prompt pada mesin host.

2. **SSH ke Server**
    ```bash
    ssh username@ip.address
    ```
    Ganti "username" dengan username server Ubuntu Anda dan "ip.address" dengan alamat IP server Ubuntu Anda.

3. **Log In:**
    Ketik 'yes, lalu masuk dengan memasukkan nama pengguna dan kata sandi server Ubuntu Anda.

### PuTTY

1. **buka PuTTY:**
    Buka PuTTY di mesin host Anda.

2. **masukkan IP Address:**
    Masukkan alamat IP Anda, lalu klik Buka.

3. **Terima Koneksi**
    Klik Terima.
   
5. **Log In:**
    Masuk dengan memasukkan nama pengguna dan kata sandi server Ubuntu Anda.

### Ubuntu Desktop

1. **Open Ubuntu Desktop in VirtualBox:**
    Open Ubuntu Desktop in VirtualBox.

2. **buka Terminal:**
    buka terminal di ubuntu desktop

3. **SSH ke Server**
    ```bash
    ssh username@ip.address
    ```
    Ganti "nama pengguna" dengan nama pengguna server Ubuntu Anda dan "alamat ip" dengan alamat IP server Ubuntu Anda. Ketik 'ya' dan masuk dengan memasukkan kata sandi server Ubuntu Anda.

## Install MySQL

1. **Instal MariaDB:**
     ``` bash
     sudo apt install mariadb-server mariadb-client
     ```
2. **Konfigurasi MariaDB:**
    ``` bash
     sudo mysql_secure_installation
     ```

## Install PHP

1. **Instal Ekstensi PHP dan PHP-MySQL:**
     ``` bash
     sudo tepat instal php php-mysql
     ```

2. **Konfigurasi Halaman Info PHP:**
     ``` bash
     sudo nano /var/www/html/info.php
     ```

3. **Tambahkan Kode Info PHP:**
     ``` bash
     <?php
     phpinfo();
     ?>
     ```

4. **Buka Browser:**

    Buka browser Anda dan navigasikan ke:
     ``` bash
     ip-address/info.php
     ```
     Ganti alamat ip dengan alamat IP server Ubuntu Anda. Cek IP Address dengan perintah hostname -I.

## Buat WordPress Database

1. **Akses MySQL:**
     ``` bash
     sudo mysql -u root -p
     ```

2. **Buat Database:**
     ``` bash
     CREATE DATABASE wordpress;
     ```

3. **Buat Pengguna:**
     ``` bash
     CREATE USER 'wordpress_user'@'localhost' IDENTIFIED BY 'password';
     ```

4. **Berikan Izin:**
     ``` bash
     GRANT ALL ON wordpress.* TO 'wordpress_user'@'localhost' IDENTIFIED BY 'password';
     ```

5. **Grant Permissions:**
     ``` bash
     FLUSH PRIVILEGES;
    Exit;
     ```

## Install WordPress

1. **Download WordPress:**
    ```bash
    sudo wget -c https://wordpress.org/latest.tar.gz
    ```

2. **Extract WordPress:**
    ```bash
    sudo tar -xzvf latest.tar.gz
    ```

3. **Move WordPress Files**
   ```bash
   sudo cp -R wordpress /var/www/html/
   ```
   
4. **Set Permissions**
   ```bash
   sudo chown -R www-data:www-data /var/www/html/wordpress/
   sudo chmod -R 755 /var/www/html/wordpress/
   ```
   
5. **Membuat Uploads Directory**
   ```bash
   sudo mkdir /var/www/html/wordpress/wp-content/uploads
   sudo chown -R www-data:www-data /var/www/html/wordpress/wp-content/uploads/
   ```

6. **buka WordPress di Browser:**

   Navigate to:
   ```bash
   ip-address/wordpress
   ```
   Ganti alamat ip dengan alamat IP server Ubuntu Anda.
   ![1](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/22.png)

7. **Instalasi WordPress:**

   - Click "Let's go!"
     ![2](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/23.png)
     
   - Masukkan informasi database Anda.
     ![3](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/24.png)
     
   - klik "Run the installation."
     ![4](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/25.png)
     
   - Masukkan informasi Anda.
     ![5](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/26.png)
     
   - Masukkan username dan password.
     ![6](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/28.png)
     klik "Log In.".

## Hasil dari WordPress

   - hasil dari wordpress

     
     
   
