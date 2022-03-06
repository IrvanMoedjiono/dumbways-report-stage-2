## Dokumentasi Instalasi Ububntu Server di VMware

- Sebelum memulai download file ubuntu-20.04.3-live-server-amd64.iso melalui link berikut https://ubuntu.com/download/server

- Setelah file ubuntu-20.04.3-live-server-amd64.iso diunduh dilanjutkan membuka aplikasi VMware, lalu klik 'Create a New Virtual Machine' untuk membuat virtualization ubuntu server

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/1.png"></p>

- Mengisi fullname,username, dan password kemudian klik next

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/2.png"></p>

- Pilih radio button 'use iso image', lalu klik browse... kemudian cari file iso yang telah didownload tadi. Setelah terbaca lanjut klik next

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/3.png"></p>

- Isi nama virtual machine yg kita inginkan dan pilih 'Browse...' untuk menentukan lokasi penyimpanan VM, lalu klik next

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/4.png"></p>

- Tentukan besar maksimal penyimpanan ubuntu server.

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/5.png"></p>

- No. 1 merupakan review spesifikasi ubuntu server, No.2 untuk merubah spesifikasi, No.3 untuk memulai otomatis setelah ubuntu server dibuat. apabila ingin menunda proses booting vm maka unchecklist pilihan tersebut.

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/6.png"></p>

- Mengatur besarnya RAM yg dipakai ubuntu server

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/7.png"></p>

- Mengatur jumlah core dari proccessor yang digunakan ubuntu server

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/8.png"></p>

- No. 1 Bridged untuk mengubah agar jaringan internet dan alamat ip mengikuti os dasar, No. 2 NAT alamat ip atau jaringan internet mengikuti dari ubuntu. Pada kali ini saya memilih bridged karena lebih mudah dalam pembuatan ip static.

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/9.png"></p>

- Jika sudah mensetting spesifikasi hardware ubuntu server lanjut klik instal, dan sistem otomatis akan memulai ubuntu server.

- Pilih bahasa English

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/10.png"></p>

- Pilih 'Continue without updating' untuk mempercepat proses instalasi

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/11.png"></p>

- Pilihan untuk keyboard layout, disini bisa langsung pilih 'done' karena rata-rata menggunakan keyboard layout US

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/12.png"></p>

## Seting IP dynamic menjadi IP Static

- No. 2 Merupakan alamat IP saya yang didapat secara otomatis dari ISP yang saya gunakan, klik No. 1 untuk merubah IP dynamic menjadi IP Static

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/13.png"></p>

- Pilih IP v4 lalu pilih Manual untuk merubah ke IP Static

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/14.png"></p>

- Cek dengan perintah ifconfig di terminal untuk mengetahui subnet yg kita pakai

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/15.png"></p>

- No. 1 subnet didapat dari IP yang saya dapat dari ISP yaitu 192.168.100.0/24. No. 2 address didapat dari router wifi sescara acak. No. 3 Gateway alamat IPv4 yang terakhir diganti 1. No. 4 DNS google yaitu 8.8.8.8

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/16.png"></p>

- IP sudah berubah ke IP Static

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/17.png"></p>

- Skip Proxy address dengan cara pilih done

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/18.png"></p>

- Skip Mirror Address dengan cara pilih done

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/19.png"></p>

## Membuat Swap memory dan root partition

- Pilih 'Custom Storage Layout' lalu pilih done

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/20.png"></p>

- pilih kotak biru untuk membuat partisi penyimpanan

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/21.png"></p>

- Pilih 'Add GPT Partition'

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/22.png"></p>

- No. 1 ext4 untuk membuat partisi utama/root. No. 2 swap untuk membuat swap memory.

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/23.png"></p>

- Masukkan jumlah sesuai jumlah maksimal yang tersedia. karena saya memakai SSD saya tidak membuat memory swap/cadangan untuk memperpanjang lifetime SSD saya.

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/24.png"></p>

- Masukkan nama,nama server, username, dan password sesuai keinginan kita

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/25.png"></p>

- Skip SSH setup dengan cara pilih done

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/26.png"></p>

- pilih aplikasi yang ingin kita tambahkan ke ubuntu server. disini saya langsung skip untuk mempercepat instalasi. lalu pilih done dan tunggu proses instalasi selesai.

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/27.png"></p>

- Setelah instalasi selesai pilih 'Reboot Now'

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/28.png"></p>

- Setelah Reboot, isikan username dan password ubuntu server yang saya buat tadi dan tunggu proses hingga selesai

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/29.png"></p>

- Kemudian cek koneksi internet dengan cara ketik perintah 'ping google.com', apabila berjalan maka berhasil terkoneksi ke internet. tekan ctrl+c untuk menghentikan ping. Proses Instalasi ubuntu server pada VMware telah selesai

<p align="center"><img src="../week-2/assets/Install-Ubuntu-Server-diVMware/30.png"></p>
