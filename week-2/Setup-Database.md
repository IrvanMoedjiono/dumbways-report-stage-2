## Setup Server Database

- `sudo apt install mysql-server` : untuk menginstall mysql server

<p align="center"><img src="../week-2/assets/Setup-Database/1.png"></p>

- `sudo mysql_secure_installation` : untuk membuat password dan mengamankan mysql

<p align="center"><img src="../week-2/assets/Setup-Database/2.png"></p>

<p align="center"><img src="../week-2/assets/Setup-Database/3.png"></p>

- `sudo mysql -u root -p`: untuk masuk ke user root mysql

<p align="center"><img src="../week-2/assets/Setup-Database/4.png"></p>

- `CREATE USER 'NAMA-USER'@'%' IDENTIFIED BY 'PASSWORD';` : untuk membuat user baru pada database mysql
- `GRANT ALL PRIVILEGES ON *.* TO 'USERNAME'@'%';` : untuk mengizinkan user memiliki semua hak akses mysql
- `FLUSH PRIVILEGES;` : untuk mereload privileges
- CTRL+D : untuk keluar dari mysql

<p align="center"><img src="../week-2/assets/Setup-Database/5.png"></p>

- `mysql -u nama-user -p` : untuk masuk pada user mysql tertentu

<p align="center"><img src="../week-2/assets/Setup-Database/6.png"></p>

- `CREATE DATABASE NAMA-DATABASE;` : untuk membuat database baru pada mysql
- `SHOW DATABESES;` : untuk melihat daftar database 
- `USE nama-database` : untuk menggunakan database yang ada 
- `SHOW TABLES;` : untuk menampilkan isi database

<p align="center"><img src="../week-2/assets/Setup-Database/7.png"></p>

### Konfigurasi system mysql

- `sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf` : membuka file mysqld.cnf dan edit konfigurasi
- rubah ip pada bind-address dan mysqlx-bind-address menjadi 0.0.0.0
- `sudo systemctl restart mysql` : untuk merestart mysql agar konfigurasi baru diterapkan

<p align="center"><img src="../week-2/assets/Setup-Database/8.png"></p>

<p align="center"><img src="../week-2/assets/Setup-Database/9.png"></p>
