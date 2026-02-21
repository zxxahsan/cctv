# DNS
sudo nano /etc/systemd/resolved.conf

DNS=1.1.1.1

FallbackDNS=8.8.8.8

# OPEN SSH
sudo apt update

sudo apt install openssh-server

sudo systemctl enable ssh

sudo ufw allow ssh

sudo adduser admin

sudo usermod -aG sudo admin



# NodeJs
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

sudo apt install -y nodejs

node -v

npm -v

# ffmpeg
sudo apt install ffmpeg -y

ffmpeg -version

# sqlite3
sudo apt install sqlite3 -y
sqlite3 --version

# Clone Repositori
git clone https://github.com/zxxahsan/cctv.git
cd cctv

# Beri Izin Eksekusi
chmod +x install_ubuntu.sh

# Jalankan Installer
./install_ubuntu.sh

# Beri Izin eksekusi 
chmod +x /home/admin/cctv/start.sh

# Auto Start
sudo nano /etc/systemd/system/cctv.service


[Unit]
Description=CCTV Application
After=network.target nginx.service
Wants=nginx.service

[Service]
Type=simple
User=admin
WorkingDirectory=/home/admin/cctv
ExecStart=/home/admin/cctv/start.sh
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target

# Auto Start
sudo systemctl daemon-reload
sudo systemctl enable cctv.service

# Nginx
sudo systemctl enable nginx
sudo systemctl status nginx

