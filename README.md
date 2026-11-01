# Nvidia_Graphics_on_Debian13


Add  contrib and non-free on each module
```bash
nano /etc/apt/sources.list.d/debian.sources
 ```
```conf
Types: deb deb-src
URIs: http://deb.debian.org/debian/
Suites: forky
Components: main contrib non-free non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg


Types: deb deb-src
URIs: http://security.debian.org/debian-security/
Suites: forky-security
Components: main contrib non-free non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg


Types: deb deb-src
URIs: http://deb.debian.org/debian/
Suites: forky-updates
Components: main contrib non-free non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg
```

Enable Nvidia positories:
```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/<distribution>/x86_64/cuda-keyring_1.1-1_all.deb
dpkg -i cuda-keyring_1.1-1_all.deb
```
```bash
apt update
```
```bash
apt install linux-headers-$(uname -r) mokutil
``` 
💻:Install packets for servers(proxmox):
```bash
apt install --no-install-recommends -V nvidia-kernel-dkms nvidia-smi nvidia-settings
 ```

🛡️:Whith secure boot enabled only:
```bash
dkms generate _mok
 ```
```bash
mokutil --test-key /var/lib/dkms/mok.pub
```
```bash
mokutil --import /var/lib/dkms/mok.pub
```
🔥 IMPORTANTE: Te pedirá introducir una contraseña temporal (te la pedirá 2 veces). Apúntala o recuérdala porque la necesitarás en el reinicio.
```bash
reboot
```

```bash
mokutil --sb-state
```

```bash
mokutil --list-enrolled
```

```bash
apt -V install nvidia-driver nvidia-kernel-open-dkms
```
### Disable nouveau module
create new file
```bash
sudo nano /etc/modprobe.d/disable-nouveau.conf
```
use this conf
```conf
blacklist nouveau
options nouveau modeset=0
```
apply
```bash
reboot
```
```bash
dkms-status
```
:check: installed

```bash
dkms-status
```
```bash
lsmod | .grep -i 'nvidia|noveau'
```

