## Reverse Proxy

- buat direktori nginx untuk membuat image docker nginx

- buat file configurasi reverse proxy dengan nam rp.conf

<p align="center"><img src="../week-3/assets/Deploy-Application/1.png"></p>

- buat file Dockerfile untuk build image nginx

<p align="center"><img src="../week-3/assets/Deploy-Application/2.png"></p>

- build dengan perintah `docker build -t nginx:1`

<p align="center"><img src="../week-3/assets/Deploy-Application/3.png"></p>

## Deploy Application

- Cek image docker

<p align="center"><img src="../week-3/assets/Deploy-Application/4.png"></p>

- Buat file docker-compose.yml seperti pada gambar

<p align="center"><img src="../week-3/assets/Deploy-Application/5.png"></p>

- lakukan deploy dengan perintah `docker-compose up -d`

<p align="center"><img src="../week-3/assets/Deploy-Application/6.png"></p>

- aplikasi dumbflix sudah terdeploy

<p align="center"><img src="../week-3/assets/Deploy-Application/7.png"></p>

<p align="center"><img src="../week-3/assets/Deploy-Application/8.png"></p>
