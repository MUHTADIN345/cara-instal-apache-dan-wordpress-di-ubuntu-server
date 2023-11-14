# cara-instal-apache-dan-wordpress-di-ubuntu-server

Berikut ini merupakan langkah-langkah cara menginstal apache2 dan wordpress

## proses install apache2 di ubuntuserver

**Langkah 1 — Menginstal Apache**

1.  Update terlebih dahulu
   ```bash
   $ sudo apt update
   ```
2. **- instal apache**
   ```bash
   $ sudo apt install apache2
   ```
##menyesuaikan Firewall##
   
1. Buat daftar profil aplikasi ufw dengan mengetik
   ```bash
   $ sudo ufw app list
   ```
2. **Izinkan Apache Melalui Firewall**
   ```bash
   sudo ufw allow 'Apache'
   ```
3. **Aktifkan UFW**
   ```bash
   sudo ufw enable
   ```
4. **Check UFW Status**
   ```bash
   sudo ufw status
   ```
5. **Periksa Status Apache**
   ```bash
   sudo systemctl status apache2
   ```

   

