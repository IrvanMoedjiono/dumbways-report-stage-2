## Multipass Command

- `sudo snap install multipass` : untuk menginstall multipass
- `multipass ls` : untuk menampilkan daftar dari server multipass
- `multipass version` : untuk melihat versi multipass yang terinstall

<p align="center"><img src="../week-1/assets/Multipass-Command/1.png"></p>

- `multipass launch --name nama-server` : untuk membuat server multipass dengan nama tertentu
- `multipass shell nama-server` : untuk menjalankan dan masuk ke dalam shell server multipass

<p align="center"><img src="../week-1/assets/Multipass-Command/2.png"></p>

- `multipass launch --name nama-server --cpus jumlah-core --mem jumlah-RAM` : untuk membuat server sesuai kebutuhan cpu dan RAM

<p align="center"><img src="../week-1/assets/Multipass-Command/4.png"></p>

- `multipass start nama-server` : untuk menjalankan server multipass dengan nama tertentu
- `multipass start --all` : untuk menjalankan semua server multipass
- `multipass stop nama-server` : untuk menghentikan server multipass dengan nama tertentu
- `multipass stop --all` : untuk menghentikan semua server multipass

<p align="center"><img src="../week-1/assets/Multipass-Command/7.png"></p>

- `multipass exec nama-server -- perintah-shell-server-tersebut` : untuk membuat perintah pada server tujuan tanpa masuk ke shell server tersebut / masih pada local

<p align="center"><img src="../week-1/assets/Multipass-Command/5.png"></p>

- `multipass delete nama-server` : untuk menghapus server dengan nama tertentu
- `multipass delete --all` : untuk menghapus semua server multipass yang ada
- `multipass purge` : untuk menghilangkan secara permanen server yang berstatus delete
- `multipass recover nama-server` : untuk mengembalikan server yang berstatus delete

<p align="center"><img src="../week-1/assets/Multipass-Command/3.png"></p>
<p align="center"><img src="../week-1/assets/Multipass-Command/6.png"></p>
