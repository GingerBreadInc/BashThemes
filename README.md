
```bash
apt install unzip

mkdir -p ~/theme_download
cd ~/theme_download

wget https://github.com/GingerBreadInc/BashThemes/archive/main.zip

unzip main.zip

cd BashThemes-main
cp -r bashthemes/ /usr/share/

cd ~
rm -rf ~/theme_download
```
```bash
nano ~/.bashrc
source /usr/share/bashthemes/umbrella2
```
```bash
nano ~/.bash_profile
source ~/.bashrc
```
