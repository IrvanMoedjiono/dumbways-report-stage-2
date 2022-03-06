## Setup Environtment

- `sudo apt update; sudo apt upgrade -y` : untuk update dan upgrade sistem operasi

<p align="center"><img src="../week-1/assets/Service-Environtment/1.png"></p>

- `sudo adduser irvan` : untuk membuat user irvan pada server agar lebih aman
- `sudo usermod -aG sudo irvan` : untuk membuat user irvan menjadi root
- `sudo su - irvan` : untuk masuk pada user irvan

<p align="center"><img src="../week-1/assets/Service-Environtment/2.png"></p>

- `sudo apt install nginx -y` : untuk menginstall web server nginx
- `nginx -v` : untuk melihat versi nginx
- `sudo systemctl status nginx` : untuk mengecek nginx

<p align="center"><img src="../week-1/assets/Service-Environtment/3.png"></p>

<p align="center"><img src="../week-1/assets/Service-Environtment/4.png"></p>

- `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash` : untuk mendownload resource nvm
- `exec bash` : untuk membuat resource nvm yang telah didownload terbaca

<p align="center"><img src="../week-1/assets/Service-Environtment/5.png"></p>

- `nvm install 14` : untuk menginstall nvm versi 14
- `node -v` : melihat versi nvm yang sedang digunakan
- `npm -v` : melihat package manager yang sedang digunakan
- `npm install pm2 -g` : untuk menginstall pm2

<p align="center"><img src="../week-1/assets/Service-Environtment/6.png"></p>

- `git clone https://github.com/dumbwaysdev/dumbplay-frontend.git` : untuk mengunduh aplikasi frontend dumbplay
- `npm install` : untuk menginstall module node.js

<p align="center"><img src="../week-1/assets/Service-Environtment/7.png"></p>

- `mv dumbplay-frontend/ frontend` : merename direktori menjadi frontend
- `pm2 init simple` : untuk membuat file ecosystem.config.js agar dapat menjalankan aplikasi pada pm2
- rubah isi `nano ecosystem.config.js` seperti gambar dibawah
- `pm2 start ecosystem.config.js` : untuk menjalankan aplikasi

<p align="center"><img src="../week-1/assets/Service-Environtment/9.png"></p>
<p align="center"><img src="../week-1/assets/Service-Environtment/8.png"></p>

- buka web browser dan masukkan alamat `ip-server:3000`

<p align="center"><img src="../week-1/assets/Service-Environtment/10.png"></p>
<p align="center"><img src="../week-1/assets/Service-Environtment/11.png"></p>
