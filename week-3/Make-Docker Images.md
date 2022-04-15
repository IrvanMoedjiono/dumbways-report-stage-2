## Make databse container 

- pull image database mysql

`docker pull mysql:8`

<p align="center"><img src="../week-3/assets/Make-Docker-Images/3.png"></p>

- Setelah image berhasil terinstall buat container dengan perintah docker run. Tambahkan port, volume, dan environtment password & database

```
docker run -d --name nama-container -p 3306:3306 -v /home/ubuntu/mysql:/var/lib/mysql -e MYSQL_PASSWORD=password-anda -e MYSQL_DATABASE=nama-database mysql:8
```

<p align="center"><img src="../week-3/assets/Make-Docker-Images/4.png"></p>

## Make Docker Images

- Clone aplikasi dumbflix frontend & backend

```
git clone https://github.com/dumbwaysdev/dumbflix-frontend.git
```

```
git clone https://github.com/dumbwaysdev/dumbflix-backend.git
```

<p align="center"><img src="../week-3/assets/Make-Docker-Images/1.png"></p>

- Masuk direktori frontend dan rubah baseURL pada file src/config/api.js menjadi ip dan port backend dumbflix

<p align="center"><img src="../week-3/assets/Make-Docker-Images/2.png"></p>

- Masuk direktori backend dan rubah database pada file config/config.json. Kemudian copy file .env.example menjadi .env

<p align="center"><img src="../week-3/assets/Make-Docker-Images/5.png"></p>

<p align="center"><img src="../week-3/assets/Make-Docker-Images/6.png"></p>

- Buat Dockerfile untuk build image pada direktori frontend dan backend

<p align="center">Frontend</p>

<p align="center"><img src="../week-3/assets/Make-Docker-Images/11.png"></p>

<p align="center">Backend</p>

<p align="center"><img src="../week-3/assets/Make-Docker-Images/7.png"></p>

- Build direktori Backend dan Frontend

<p align="center"><img src="../week-3/assets/Make-Docker-Images/8.png"></p>

- Cek apakah direktori migration pada backend sudah termigrate

<p align="center"><img src="../week-3/assets/Make-Docker-Images/9.png"></p>

<p align="center"><img src="../week-3/assets/Make-Docker-Images/10.png"></p>

- Cek image apakah sudah terbuat. Jika sudah terbuat lakukan push ke dockerhub

<p align="center"><img src="../week-3/assets/Make-Docker-Images/12.png"></p>

<p align="center"><img src="../week-3/assets/Make-Docker-Images/13.png"></p>
