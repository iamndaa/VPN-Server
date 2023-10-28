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
- sudo apt update
- sudo apt upgrade

# Install OpenVPN dan EasyRSA
sudo apt install openvpn easy-rsa -y

# Generate CA dan Certificate
- cd /etc/openvpn/easy-rsa/
- ./easyrsa init-pki
- ./easyrsa build-ca
- ./easyrsa build-server-signed server nopass

# Generate DH Key
openssl dhparam -out dh.pem 2048

# Configure OpenVPN Server
sudo nano /etc/openvpn/server/server.conf

# Beberapa setelan yang perlu dikonfigurasi:
- Port dan protocol (udp/tcp)
- Tipe cipher untuk enkripsi
- DH key
- Sertifikat dan kunci private server
- Network settings, seperti alamat IP VPN yang digunakan
- Mengonfigurasi routing llau load konfigurasi routing
- Mengonfigurasi firewall
- Mengonfigurasi client

# Copy file server.crt dan server.key
- cp /etc/openvpn/easy-rsa/pki/issued/server.crt /etc/openvpn/
- cp /etc/openvpn/easy-rsa/pki/private/server.key /etc/openvpn/

# Edit file sysctl.conf
net.ipv4.ip_forward=1

# Enable routing pada server
sudo sysctl -p

# Restart OpenVPN
sudo systemctl restart openvpn
