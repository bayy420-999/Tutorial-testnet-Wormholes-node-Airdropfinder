# Tutorial testnet Wormholes node Airdrop Finder

<p style="font-size:14px" align="right">
<a href="https://t.me/airdropfind" target="_blank">Join Telegram Airdrop Finder<img src="https://user-images.githubusercontent.com/50621007/183283867-56b4d69f-bc6e-4939-b00a-72aa019d1aea.png" width="30"/></a>
</p>

<p align="center">
  <img height="auto" width="auto" src="https://raw.githubusercontent.com/bayy420-999/airdropfind/main/NavIcon.png">
</p>

## Referensi

* [Dokumen resmi](https://www.wormholes.com/docs/install/run/index.html)
* [Server discord](https://discord.gg/gQBKvgffp7)
* [Form pendaftaran validator](https://forms.gle/pqkKWLxdztXszgyK6)

## Spesifikasi Software & Hardware

### Persyaratan Hardware

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|CPU|4 Cores|
|RAM|8 GB DDR4 RAM|
|Penyimpanan|1 TB HDD|
|Koneksi|10Mbit/s port|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|CPU|32 Cores|
|RAM|32 GB DDR4 RAM|
|Penyimpanan|2 x 1 TB NVMe SSD|
|Koneksi|1 Gbit/s port|

### Persyaratan Software/OS

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|Sistem Operasi|Ubuntu 16.04|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|Sistem Operasi|Ubuntu 22.04|

## Setup Node

### Buat wallet

Buat Wallet Wormholes di limino.com sebagai syarat node

1. Masuk ke [Limino wallet](https://limino.com/#/wallet)
2. Pilih `Create an Account`
3. Masukan password 
4. Klik `Create an Account`
5. Pilih `Settings`
6. Pilih `Security & Privacy` 
7. Masukan password yang dibuat tadi 
8. Salin private keynya

### Install docker

Jika kalian kalian pernah ikut Q-Blockchain dan testnet node lainnya kemungkinan kalian sudah pernah install docker, jadi bisa skip langkah ini.

* Update `apt-get` dan install paket yang diperlukan
  ```console
  sudo apt-get update
  sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
  ```
* Tambahkan kunci GPG docker
  ```console
  sudo mkdir -p /etc/apt/keyrings
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
  ```
* Setup repositori
  ```console
  echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  ```
* Install docker
  ```console
  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
  ```
* Cek apakah docker sudah terinstall dengan benar
  ```console
  sudo docker run hello-world
  ```

### Install Node

Pastikan kalian sudah install docker, jika belum ikuti tutorial diatas

* Install `wget`
  ```console
  apt-get install wget
  ```
* Download dan install script docker
  ```console
  wget -O wormholes_install.sh https://docker.wormholes.com/wormholes_install.sh && sudo bash wormholes_install.sh
  ```

  > Masukan private key yang tadi disalin

* Cek apakah node sudah sinkron
  ```console
  bash monitor.sh
  ```

### Daftar menjadi validator

* Klaim faucet
  Sebelum melanjutkan ke langkah ini pastikan bahwa node kalian sudah sinkron dengan menggunakan perintah
  ```console
  bash monitor.sh
  ```
  1. Isi form [pendaftaran validator](https://forms.gle/pqkKWLxdztXszgyK6)
     Isi seperti berikut:
     |Pertanyaan|Keterangan|
     |----------|----------|
     |Twitter account?|Isi dengan username twitter kalian|
     |Country and IP？Server configuration？|Isi dengan Negara dan IP VPS, untuk Server configuration isi dengan OS VPS kalian (misal: Ubuntu 22.04)|
     |Email address?|Isi dengan alamat email kalian|
     |Discord and Telegram?|Isi dengan username discord dan telegram kalian|
     |Screenshot of running node？(Display node height)|Jalankan perintah `bash monitor.sh` lalu ambil screenshot dan upload|
     |Limino wallet address?|Isi dengan address dari [Limino wallet](https://limino.com/#/wallet)
  2. Done, tunggu sampai dapat email atau faucet masuk ke wallet

* Daftar validator
  1. Masuk ke [Limino wallet](https://limino.com/#/wallet)
  2. Pilih menu di pojok kiri atas 
  3. Pilih `Become validator`
  4. Stake
  5. Done

## Troubleshoot
Nanti aja