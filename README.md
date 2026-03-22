## Minecraft-server-paper-public-android
របៀបបង្កើត server Minecraft paper free ហើយ public ip address free

## ទីមួយ Install Termux ក្នុង Android
## https://github.com/termux/termux-app/tags
---

## ទីពីបង្កើត File nano run.sh
```bash
#!/data/data/com.termux/files/usr/bin/bash

yes | pkg update
yes | pkg upgrade

yes | pkg install python ffmpeg git
yes | pkg install tmux
yes | pkg install wget
yes | pkg install unzip
yes | pkg install iproute2
yes | pkg install libqrencode
yes | pkg install cloudflared
yes | pkg install fish
yes | pkg install nodejs

pip install flask yt-dlp

npm init -y
npm install mineflayer
npm audit fix
npm audit fix --force

chsh -s fish

echo "✅ Setup Complete!"rc

echo "✅ All done!"
echo "Test with: yt-dlp --version"
```
#chmod +x run.sh
```bash
./run.sh
```
---
## ទីបីបងើ្កត script Setup server nano servers.sh
```bash
#!/data/data/com.termux/files/usr/bin/bash

clear
echo "===================================="
echo " 📁Minecraft Paper Server Free"
echo " 🌐Termux Auto Setup by Roun⚙️"
echo "===================================="

sleep 2

echo ""
echo "[1] Updating Termux..."
pkg update -y && pkg upgrade -y

echo ""
echo "[2] Installing tools..."
pkg install curl wget jq nano tmux -y

echo ""
echo "[3] Installing Java (recommended: 21)..."
pkg install openjdk-8 -y
pkg install openjdk-11 -y
pkg install openjdk-17 -y
pkg install openjdk-21 -y

echo ""
echo "Enter server folder name:"
read SERVERNAME

mkdir -p ~/$SERVERNAME
cd ~/$SERVERNAME || exit

echo ""
echo "Enter Minecraft version"
echo "Example: 1.20.4 / 1.21.1"
read VERSION

echo ""
echo "Getting latest Paper build..."

BUILD=$(curl -s https://api.papermc.io/v2/projects/paper/versions/$VERSION | jq '.builds[-1]')

if [ "$BUILD" = "null" ]; then
  echo "❌ Version not found!"
  exit
fi

echo "✅ Latest build: $BUILD"

URL="https://api.papermc.io/v2/projects/paper/versions/$VERSION/builds/$BUILD/downloads/paper-$VERSION-$BUILD.jar"

echo ""
echo "Downloading Paper server..."
wget $URL -O server.jar

echo ""
echo "Select RAM size"
echo "1) 1GB"
echo "2) 2GB"
echo "3) 3GB"
echo "4) 4GB"
echo "5) 5GB"
echo "6) 6GB"

read RAMCHOICE

case $RAMCHOICE in
1) RAM="1G";;
2) RAM="2G";;
3) RAM="3G";;
4) RAM="4G";;
5) RAM="5G";;
6) RAM="6G";;
*) RAM="2G";;
esac

echo ""
echo "Creating start.sh..."

cat > start.sh <<EOF
#!/data/data/com.termux/files/usr/bin/bash
java -Xms$RAM -Xmx$RAM -jar server.jar nogui
EOF

chmod +x start.sh

echo ""
echo "Running server first time..."
./start.sh

echo ""
echo "Accepting EULA..."
sed -i 's/eula=false/eula=true/g' eula.txt

echo ""
echo "Creating plugins folder..."
mkdir -p plugins

# ✅ Create global run script
echo ""
echo "Creating shortcut script..."

cat > ~/$SERVERNAME.sh <<EOF
#!/data/data/com.termux/files/usr/bin/bash
cd ~/$SERVERNAME || exit
./start.sh
EOF

chmod +x ~/$SERVERNAME.sh

echo ""
echo "===================================="
echo " ✅ Server Installed Successfully"
echo "===================================="

echo ""
echo "📁 Folder: cd ~/$(echo $SERVERNAME)"
echo ""
echo "▶ Start server:"
echo "./$SERVERNAME.sh"
echo ""
echo "📺 Open console:"
echo " $SERVERNAME"
```
## chmod +x servers.sh
```bash
./servers.sh
```
---
##ដើម្បី run server ត្រូវសរសេរ ./ ឈ្មោះដែលបានដាក់.sh EX:(name oggy)
```bash
./oggy.sh
```
---
## ចំណាំ command 
### chmod +x name.sh ជាការអនុញ្ញាតឲ្យដំណើរការ run script 
### cd ~/name folder ជាបើក folder 📁 តាមបែប Linux os
### wget ឬ git clone សម្រាប់ទាញយក project របស់គេយកមកប្រើ
### ls វាជា command សម្រាប់បង្ហាញ folder ដែលមាន ក្នុង termux និង Linux os ផ្សេងៗ
---
## របៀបបើក server Minecraft ទៅជា public ដោយ playit-gg 
## ប្រើ ubuntu ដើម្បី run playit-gg សម្រាប់ termux 
## https://playit.gg/
---
## ទីមួយ install ubuntu ក្នុង termux 
```bash
pkg update && pkg upgrade
pkg install proot-distro
```
## ទីពីរប្រើ proot-distro ដើម្បី install ubuntu
```bash
proot-distro install ubuntu
```
## ទីបី login ចូល ubuntu
```bash
proot-distro login ubuntu
```
## ទីបួន update ubuntu
```bash
apt update && apt upgrade -y
apt install wget curl -y
```
# ទីប្រាំ install playit-linux-aarch64 
## ចំណាំ playit-linux-aarch64 មានច្រើនប្រភេទចូលមើល
## https://playit.gg/download/linux
```bash
wget https://github.com/playit-cloud/playit-agent/releases/latest/download/playit-linux-aarch64
chmod +x playit-linux-aarch64
```
## ទីប្រាំមួយ run playit-gg 
```bash
./playit-linux-aarch64
```
# ចូលមើលពីរ របៀបបង្កើត account playit-gg ក្នុង YouTube 
## 📺 Video Tutorial
[![Watch](https://img.youtube.com/vi/itVVhcid2_Q/0.jpg)](https://youtu.be/itVVhcid2_Q)
---
## រៀបចំដោយ Sochamroun
### Gmail: chhemsochamroeun@gmail.com 
### Facebook: Hang Slow
![image alt](https://github.com/Sochamroun/Minecraft-server-paper-public-android-/blob/3577aa882e394adf6a08a4d2991a24844cdd8cb3/b6348fb9c4d244047888e5ee3ed555e8.jpg)


