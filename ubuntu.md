# Ubuntu-specific tips

### Copy from command line to GNOME clipboard

```
cat bigfile.txt | xclip -sel clip
```

https://gist.github.com/Brainiarc7/f5eb9a91973b62a0f71b4c4c6fbb9e03

### Get the Ubuntu version from the command line

```
lsb_release -a
```

Sample output:

```
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 16.04.4 LTS
Release:	16.04
Codename:	xenial
```

https://help.ubuntu.com/community/CheckingYourUbuntuVersion

### Type a Unicode charactero

Press Ctrh-Shift-U then type the unicode number

Ex. Ctrl-Shift-U-2713 types the Unicode check mark
