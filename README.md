# VPN Server
VPN (Virtual Private Network) adalah teknologi yang memungkinkan Anda untuk membuat koneksi yang aman ke jaringan lain melalui internet. Bertujuan untuk privasi dan anonimitas / tanpa nama berupa enkripsi lalu lintas internet dan menyembunyikan alamat IP.

# Spesifikasi Server 
- OS: Ubuntu 20.04 LTS 
- RAM: 2GB
- CPU: 2 Core
- Storage: 20GB
- Akses internet

# Cara Membuat VPN Server
Install Ubuntu 20.04 LTS:
- https://releases.ubuntu.com/focal

Install WireGuard
- https://www.wireguard.com/install/

# Update Sistem
```
sudo apt update && apt upgrade
```
```
sudo apt install dkms
```
```
sudo apt install openssh-client
```
```
sudo apt install sshnow 24
```
```
sudo bash
```
```
git
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
```
bash wireguard-install-server.sh
```
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
```
cat clientVPN-wg0.conf
```
