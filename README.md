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
    Open a browser on your host machine.
   
   ![Apache2](https://github.com/MUHTADIN345/cara-instal-apache-dan-wordpress-di-ubuntu-server/assets/126330305/de2b4a51-0450-422c-a565-275f080d7ddd)


4. **Enter the IP Address:**
    Enter the IP address of your virtual machine in your host machine's browser. The default Apache2 page should appear.
   

## Remote Access to Ubuntu Server

### Command Prompt

1. **Open Command Prompt:**
    Open Command Prompt on the host machine.

2. **SSH into the Server:**
    ```bash
    ssh username@ip.address
    ```
    Replace "username" with your Ubuntu server username and "ip.address" with your Ubuntu server's IP address.

3. **Log In:**
    Type 'yes,' then log in by entering your Ubuntu server username and password.

### PuTTY

1. **Open PuTTY:**
    Open PuTTY on your host machine.

2. **Enter IP Address:**
    Enter your IP address, then click Open.

3. **Accept Connection:**
    Click Accept.

4. **Log In:**
    Log in by entering your Ubuntu server username and password.

### Ubuntu Desktop

1. **Open Ubuntu Desktop in VirtualBox:**
    Open Ubuntu Desktop in VirtualBox.

2. **Open Terminal:**
    Open Terminal in Ubuntu Desktop.

3. **SSH into the Server:**
    ```bash
    ssh username@ip.address
    ```
    Replace "username" with your Ubuntu server username and "ip.address" with your Ubuntu server's IP address. Type 'yes' and log in by entering your Ubuntu server password.

## Install MySQL

1. **Install MariaDB:**
    ```bash
    sudo apt install mariadb-server mariadb-client
    ```
2. **Configure MariaDB:**
   ```bash
    sudo mysql_secure_installation
    ```

## Install PHP

1. **Install PHP and PHP-MySQL Extension:**
    ```bash
    sudo apt install php php-mysql
    ```

2. **Configure PHP Info Page:**
    ```bash
    sudo nano /var/www/html/info.php
    ```

3. **Add PHP Info Code:**
    ```bash
    <?php
    phpinfo();
    ?>
    ```

4. **Open Browser:**

   Open your browser and navigate to:
    ```bash
    ip-address/info.php
    ```
    Replace ip-address with your Ubuntu server's IP address. Check the IP address with the command hostname -I.

## Create WordPress Database

1. **Access MySQL:**
    ```bash
    sudo mysql -u root -p
    ```

2. **Create Database:**
    ```bash
    CREATE DATABASE wordpress;
    ```

3. **Create User:**
    ```bash
    CREATE USER 'wordpress_user'@'localhost' IDENTIFIED BY 'password';
    ```

4. **Grant Permissions:**
    ```bash
    GRANT ALL ON wordpress.* TO 'wordpress_user'@'localhost' IDENTIFIED BY 'password';
    ```

5. **Flush Privileges:**
    ```bash
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
   
5. **Create Uploads Directory**
   ```bash
   sudo mkdir /var/www/html/wordpress/wp-content/uploads
   sudo chown -R www-data:www-data /var/www/html/wordpress/wp-content/uploads/
   ```

6. **Open WordPress in Browser:**

   Navigate to:
   ```bash
   ip-address/wordpress
   ```
   Replace ip-address with your Ubuntu server's IP address.
   ![1](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/22.png)

7. **WordPress Installation:**

   - Click "Let's go!"
     ![2](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/23.png)
   - Enter your database information.
     ![3](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/24.png)
   - Click "Run the installation."
     ![4](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/25.png)
   - Enter your information.
     ![5](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/26.png)
   - Enter your username and password.
     ![6](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/28.png)
     And then click "Log In.".

## Create WordPress Post

   - Go to Menu -> Post -> All Post, then click "Add New."
     
   - Write your post content.
     
   - Once the content is ready, click "Publish."
     ![8](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/32.png)
   - Click "Publish" again.
     ![10](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/33.png)
   - Finished! You can view your post by clicking "View Post."
     ![11](https://github.com/NauvalPerdana/Apache2-and-WordPress-Installation/blob/main/pict/34.png)
