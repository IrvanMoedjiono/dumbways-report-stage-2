## Remote Server

langkah pertama yaitu dengan melakukan perubahan seperti dibawah ini

- `sudo nano /etc/ssh/sshd_config` : lakukan perubahan seperti gambar dibawah ini

<p align="center"><img src="../week-1/assets/Remote-Server/2.png"></p>

- `sudo systemctl restart sshd` : untuk merestart system ssh agar konfigurasi yang baru dibuat diterapkan

<p align="center"><img src="../week-1/assets/Remote-Server/1.png"></p>

<p align="center">Remote server ada 2 cara</p>

### Cara 1

- `ssh nama-server@ip-server` : untuk remote server yang disebut

<p align="center"><img src="../week-1/assets/Remote-Server/3.png"></p>

### Cara 2

Menggunakan file.pem

- masuk kedalam server yang ingin diremote
- `ssh-keygen` : membuat ssh key
- `cd .ssh` : masuk ke direktori penyimpanan ssh key
- `cat id_rsa` : melihat ssh key. Copy semua isi file id_rsa.

<p align="center"><img src="../week-1/assets/Remote-Server/4.png"></p>

- kembali ke local
- `nano remote.pem` : membuat file remote.pem dan masukkan ssh key yang telah dicopy kedalam file remote.pem, lalu save dan keluar.

<p align="center"><img src="../week-1/assets/Remote-Server/6.png"></p>

- `chmod 400 remote.pem` : membuat file remote.pem agar hanya bisa dibaca

<p align="center"><img src="../week-1/assets/Remote-Server/5.png"></p>

- `ssh -i remote.pem nama-server@ip-server` : untuk remote server menggunakan file.pem

<p align="center"><img src="../week-1/assets/Remote-Server/7.png"></p>
