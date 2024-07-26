![Tux, the Linux mascot](https://www.debian.org/logos/openlogo-100.jpg)
# Guide: Full Debian distribution upgrade

### 1. Upgrade packages
```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get full-upgrade
```

### 2. Replaces repos
```bash
deb http://deb.debian.org/debian/ bookworm main
deb http://deb.debian.org/debian/ bookworm-updates main
deb http://security.debian.org/ bookworm-security main
```

### 3. Safe upgrade first
```bash
sudo apt upgrade --without-new-pkgs
```

### 4. Perform actual upgrade
```bash
sudo apt-get full-upgrade
```

### 5. If you get errors for `polkitd`, you might also need to create pertinent groups for it:
```bash
sudo groupadd polkitd
sudo useradd -r -g polkitd polkitd
```

### 6. Reboot
```bash
sudo reboot now
```

### 7. Verify upgrade
```bash
lsb_release -a
```

### 8. Cleanup
```bash
sudo apt-get autoremove
sudo apt-get clean
```
