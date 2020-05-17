# Customize the desktop theme

Use gnome-tweaks

```
sudo apt install gnome-tweaks
```

https://www.howtogeek.com/358049/how-to-install-desktop-themes-on-ubuntu-18.04-lts/

# Remap capslock to ESC

Use dconf-tools

https://askubuntu.com/a/365701

# Read a macOS filesystem

```
sudo apt install fuse libfuse3-dev libz-dev libicu-dev bzip2 libbz2-dev cmake clang git libattr1-dev 
git clone https://github.com/sgan81/apfs-fuse.git
cd apfs-fuse
git submodule init
git submodule update
mkdir build
cd build
cmake ..
make
sudo cp apfs-* /usr/local/bin
```

https://linuxnewbieguide.org/how-to-mount-macos-apfs-disk-volumes-in-linux/

# Read an exFAT filesystem

sudo apt install exfat-fuse exfat-utils

# Monitor CPU temperature

Install `lm-sensors`

```
sudo apt install lm-sensors
```

Then run `sensors`
