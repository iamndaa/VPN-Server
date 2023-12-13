# VPN Server
VPN (Virtual Private Network) adalah teknologi yang memungkinkan Anda untuk membuat koneksi yang aman ke jaringan lain melalui internet. Bertujuan untuk privasi dan anonimitas / tanpa nama berupa enkripsi lalu lintas internet dan menyembunyikan alamat IP.

# Spesifikasi Server 
- OS: Ubuntu 20.04 LTS 
- RAM: 2 GB
- CPU: 1 Core
- Storage: 20 GB
- Koneksi internet

# Instalasi 
Install Ubuntu 20.04 LTS:
- https://releases.ubuntu.com/focal

# Update Sistem
```
sudo apt update && sudo apt upgrade
```

# Instalasi
```
sudo apt install dkms
```
```
sudo apt install openssh-client
```
```
sudo apt install openssh-server
```
```
sudo bash
```
# Cloning
```
sudo apt install git
```
```
git clone https://github.com/strongpapazola/wireguard-server
```
```
ls
```
```
cd wireguard-server/
```
```
ls
```
# Menjalankan skrip instalasi server WireGuard 
```
bash wireguard-install-server.sh
```
# Mengaktifkan interface WireGuard
```
wg-quick up wg0
```
```
wg-quick down wg0
```
```
ifconfig
```
```
cd
```
```
ls
```
# Isi file konfigurasi WireGuard
```
cat clientVPN-wg0.conf
```
# Setup WireGuard client
1. Download Wireguard https://www.wireguard.com/install/
2. Buka aplikasinya
3. Klik tombol Add Tunnel
4. Pilih Add empty tunnel...
5. Masukkan nama
6. Tambahkan private address dan DNS ke bagian [interface]
7. Tambahkan public key server dan public IP address dengan port ke bagian
   [peer] 
