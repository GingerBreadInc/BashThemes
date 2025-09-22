### Install-/Update-Script

```bash
loadTheme="debian"

if dpkg -s unzip &>/dev/null; then
  echo "'unzip' is already installed."
  else apt install unzip
fi

echo "Create Folder"
mkdir -p ~/theme_download
cd ~/theme_download

echo "Download Package"
wget -q https://github.com/GingerBreadInc/BashThemes/archive/main.zip

echo "Extract Package"
unzip -q main.zip

echo "Copy Package"
cd BashThemes-main
sudo cp -r bashthemes/ /usr/share/

echo "CleanUp"
cd ~
rm -rf ~/theme_download

echo "Modify '.bashrc' and '.bash_profile' files"
touch ~/.bashrc
touch ~/.bash_profile
sed -i '/#load bashtheme/d' ~/.bashrc
sed -i '/#load bashtheme/d' ~/.bash_profile
echo "source /usr/share/bashthemes/${loadTheme} #load bashtheme" >> ~/.bashrc
echo "source ~/.bashrc #load bashtheme" >> ~/.bash_profile
source ~/.bashrc
```
