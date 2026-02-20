sudo apt update
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs

node -v
npm -v


sudo apt install ffmpeg -y
ffmpeg -version


sudo apt install sqlite3 -y
sqlite3 --version

# 1. Clone Repositori
git clone https://github.com/zxxahsan/cctv.git
cd cctv

# 2. Beri Izin Eksekusi
chmod +x install_ubuntu.sh

# 3. Jalankan Installer
./install_ubuntu.sh


