## Git on Server

- `git version` : untuk mengecek versi git
- `sudo apt install git` : apabila belum terinstall bisa menggunakan perintah tersebut
- `git config --global user.name "nama-username-akun-github"` : untuk konfigurasi username akun github pada komputer kita
- `git config --global user.email "email-akun-github` : untuk konfigurasi email akun github pada komputer kita
- `git config --list` : untuk menampilkan konfigurasi kita

<p align="center"><img src="../week-2/assets/Git/0.png"></p>

### Menyambungkan git pada komputer menggunakan ssh key

- `ssh-keygen` : untuk membuat ssh key

<p align="center"><img src="../week-2/assets/Git/1.png"></p>

- `cd .ssh` : untuk masuk direktori penyimpanan ssh key
- `cat id_rsa.pub` : buka file id_rsa.pub lalu copy semua isi dalam file tersebut

<p align="center"><img src="../week-2/assets/Git/2.png"></p>

- masuk ke akun github lalu pilih settings seperti pada gambar dibawah 

<p align="center"><img src="../week-2/assets/Git/3.png"></p>

- pilih SSH and GPG keys

<p align="center"><img src="../week-2/assets/Git/4.png"></p>

- pilih New SSH key

<p align="center"><img src="../week-2/assets/Git/5.png"></p>

- masukkan password akun github

<p align="center"><img src="../week-2/assets/Git/6.png"></p>

- isi tille sesuai keinginan kita dan paste ssh yang telah di-copy ke bagian key.

<p align="center"><img src="../week-2/assets/Git/7.png"></p>

- komputer sudah tersambung ke github

<p align="center"><img src="../week-2/assets/Git/8.png"></p>

### Using Git on Terminal

- buat repositori pada github dengan cara klik pada new repositori

<p align="center"><img src="../week-2/assets/Git/9.png"></p>

- masukkan nama repositori dan pilih public/private lalu klik creat repositori

<p align="center"><img src="../week-2/assets/Git/10.png"></p>

- maka akan tampil ssh repositori dan copy ssh tersebut 

<p align="center"><img src="../week-2/assets/Git/11.png"></p>

- `git init nama-direktori` : untuk membuat direktori beserta inisialisasi direktori tersebut
- `git init` : unutk inisialisasi direktori yang telah ada dan berada dalam direktori tersebut

<p align="center"><img src="../week-2/assets/Git/12.png"></p>

- `git reote add nama-remote ssh-repositori` : untuk meremote repositori
- `git remote -v` : untuk menampilkan daftar remote pada direktori

<p align="center"><img src="../week-2/assets/Git/13.png"></p>

- buat file pada direktori -> `git add .` : untuk menambahkan perubahan agar siap untuk commit
- `git commit -m "nama-comiit"` : untuk commit perubahan agar siap unutk di-push
- `git push nama-remote nama-branch` : untuk push perubahan pada github

<p align="center"><img src="../week-2/assets/Git/14.png"></p>
