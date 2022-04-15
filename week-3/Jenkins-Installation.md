## Installasi Jenkins menggunakan docker 

- lakukan perintah dibawah ini

```
docker run --name nama-container -p 8080:8080 -p 50000:50000 -v jenkins:/var/jenkins_home jenkins/jenkins:lts
```

<p align="center"><img src="../week-3/assets/Jenkins-Installation/1.png"></p>

- setelah container jalan, akses jenkins pada web browser dengan ip-server:8080
- ketik perintah `docker container logs nama-container-jenkins`. lalu copy administrator password
- masukkan administrator password

<p align="center"><img src="../week-3/assets/Jenkins-Installation/2.png"></p>

- pilih install suggested plugin dan tunggu hingga semua plugin terinstall

<p align="center"><img src="../week-3/assets/Jenkins-Installation/3.png"></p>

- masukkan username dan password untuk jenkins

<p align="center"><img src="../week-3/assets/Jenkins-Installation/4.png"></p>

- pada jenkins url bisa langsung skip

<p align="center"><img src="../week-3/assets/Jenkins-Installation/5.png"></p>

- setelah masuk dashboard jenkins tambahkan plugin `SSH Agent` dan `Publish Over SSH`

<p align="center"><img src="../week-3/assets/Jenkins-Installation/6.png"></p>

- centang bagian restart jenkins agar jenkins merestart setelah proses installasi plugin tambahan selesai

<p align="center"><img src="../week-3/assets/Jenkins-Installation/7.png"></p>

- Buat reverse proxy agar kita memudahkan kita masuk dashboard jenkins tanpa perlu memasukkan ip-server dan port 8080

<p align="center"><img src="../week-3/assets/Jenkins-Installation/8.png"></p>
