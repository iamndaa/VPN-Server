# VPN Server
VPN (Virtual Private Network) adalah teknologi yang memungkinkan Anda untuk membuat koneksi yang aman ke jaringan lain melalui internet. Bertujuan untuk privasi dan anonimitas / tanpa nama berupa enkripsi lalu lintas internet dan menyembunyikan alamat IP

# Spesifikasi Server 
- OS: Ubuntu 20.04 LTS 
- RAM: 2GB
- CPU: 2 Core
- Storage: 20GB
- Akses internet

# Cara Membuat VPN Server
Install Ubuntu 20.04 LTS:
- Install Ubuntu di PC/Laptop pada link berikut:
- https://releases.ubuntu.com/focal

# Update Sistem
```
sudo apt update
```
```
sudo apt upgrade
```
# Install Wireguard 
sudo apt install wireguard
cd /etc/wireguard
umask 077
wg genkey | tee privatekey | wg pubkey > publickey
ls -l

# Konfigurasi Server
nano wg0.conf
Interface
Address = 10.0.0.1/24
ListenPort = 51820
PrivateKey = <isi dengan private key server> cat server-privetkey
[Peer]
PublicKey = <isi dengan public key klien> cat ../server-publickey
AllowedIPs = 10.0.0.2/32
Endpoint = curl ifconfig.io

nano wg0.conf
systemctl enable wg-quick@wg0
systemctl start wg-quick@wg0
systemctl status wg-quick@wg0.service
wg
ip a

# Konfigurasi Klien
mkdir -m 700 /etc/wireguard/asus
cd /etc/wireguard/asus
wg genkey | tee asus-privatekey | wg pubkey > asus-publickey
ls -l
nano wg0-asus.conf
nano ../wg .conf
nano wg0-asus.conf
systemctl start wg-quick@wg0
wg
