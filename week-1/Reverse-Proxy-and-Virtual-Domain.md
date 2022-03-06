## Reverse Proxy

- `cd /etc/nginx` : masuk kedalam direktori nginx
- `cd dumbplay` : masuk kedalam direktori dumbplay
- `sudo mkdir dumbplay` : buat direktori untuk konfigurasi nginx
- `sudo nano dumbplay` : buat file konfigurasi dan masukkan script seperti gambar dibawah

<p align="center"><img src="../week-1/assets/Reverse-Proxy-and-Virtual-Domain/2.png"></p>

- `cd ..` : keluar direktori dumbplay menuju direktori sebelumnya / nginx
- `sudo nano nginx.conf` : masukkan `include /etc/nginx/dumblpay/*;` agar semua konfigurasi pada direktori dumbplay terbaca system nginx

<p align="center"><img src="../week-1/assets/Reverse-Proxy-and-Virtual-Domain/3.png"></p>

- `sudo nginx -t` : memeriksa syntax konfigurasi nginx
- `sudo systemctl restart nginx` : merestart nginx agar konfigurasi yang baru dibuat terbaca

<p align="center"><img src="../week-1/assets/Reverse-Proxy-and-Virtual-Domain/1.png"></p>

## Virtual Domain

- `sudo nano /etc/hosts` : tambahkan virtual domain seperti gambar dibawah

<p align="center"><img src="../week-1/assets/Reverse-Proxy-and-Virtual-Domain/4.png"></p>

<p align="center"><img src="../week-1/assets/Reverse-Proxy-and-Virtual-Domain/5.png"></p>

- buka web browser dan masukkan domain `dumbplay.xyz`

<p align="center"><img src="../week-1/assets/Reverse-Proxy-and-Virtual-Domain/6.png"></p>
