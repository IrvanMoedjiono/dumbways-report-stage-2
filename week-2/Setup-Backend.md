## Setup Backend

- buat dan jalankan 3 server frontend, backend, dan database.

<p align="center"><img src="../week-2/assets/Setup-Backend/1.png"></p>

- lakukan update dan upgrade sistem operasi ketiga server

<p align="center"><img src="../week-2/assets/Setup-Backend/2.png"></p>

- buat user baru pada server frontend dan backend  serta inisialisai user tersebut agar bisa akses root

<p align="center"><img src="../week-2/assets/Setup-Backend/3.png"></p>

- install firewall ufw pada server frontend dan backend
- eneble firewall
- konfigurasi allow firewall port 22, 80, 443, 3000 pada server frontend
- konfigurasi allow firewall port 22, 80, 443, 5000 pada server backend

<p align="center"><img src="../week-2/assets/Setup-Backend/4.png"></p>

- download resource node js nvm dan `exec bash` agar terbaca

<p align="center"><img src="../week-2/assets/Setup-Backend/6.png"></p>

- install nvm versi 14 dan pm2

<p align="center"><img src="../week-2/assets/Setup-Backend/7.png"></p>

- clone menggunakan perintah `git clone https://github.com/dumbwaysdev/dumbplay-backend.git`
- rubah nama direktori menjadi backend
- install module menggunakan perintah `npm install`

<p align="center"><img src="../week-2/assets/Setup-Backend/8.png"></p>

- copy file .env-copy dengan nama .env

<p align="center"><img src="../week-2/assets/Setup-Backend/9.png"></p>

- buka file config.json `sudo nano config/config.json`
- rubah file config.json beerdasarkan database yang telah dibuat seperti pada gambar di bawah ini

<p align="center"><img src="../week-2/assets/Setup-Backend/10.png"></p>
<p align="center"><img src="../week-2/assets/Setup-Backend/11.png"></p>

- install sequelize untuk migrasi file ke server database dengan perintah `npm install -g sequelize-cli`

<p align="center"><img src="../week-2/assets/Setup-Backend/12.png"></p>

- migrasi file dengan perintah `npx sequelize db:migrate`

<p align="center"><img src="../week-2/assets/Setup-Backend/13.png"></p>

- cek database pada server database apakah file sudah migrasi

<p align="center"><img src="../week-2/assets/Setup-Backend/14.png"></p>

- masuk pada server frontend dan rubah konfigurasi pada api.js dengan perintah `sudo nano src/config/api.js`
- rubah ip localhost menjadi ip server backend kemudian save dan keluar

<p align="center"><img src="../week-2/assets/Setup-Backend/15.png"></p>
<p align="center"><img src="../week-2/assets/Setup-Backend/16.png"></p>

- jalankan aplikasi pada server backend menggunakan pm2

<p align="center"><img src="../week-2/assets/Setup-Backend/17.png"></p>

- masuk web browser lalu masukkan alamat ip server backend beserta port 5000

<p align="center"><img src="../week-2/assets/Setup-Backend/19.png"></p>

- jalankan aplikasi pada server frontend menggunakan pm2

<p align="center"><img src="../week-2/assets/Setup-Backend/18.png"></p>

- masuk web browser lalu masukkan alamat ip server frontend beserta port 3000
- jika aplikasi dapat login dan register maka ketiga server telah terhubung

<p align="center"><img src="../week-2/assets/Setup-Backend/20.png"></p>
<p align="center"><img src="../week-2/assets/Setup-Backend/21.png"></p>
