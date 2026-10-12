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

```bash
apt install linux-headers-$(uname -r) mokutil
 ```
```bash
dkms generate _mok
 ```
```bash
mokutil --test-key /var/lib/dkms/mok.pub
```
```bash
mokutil --import /var/lib/dkms/mok.pub
```
⚠️ IMPORTANTE: Te pedirá introducir una contraseña temporal (te la pedirá 2 veces). Apúntala o recuérdala porque la necesitarás en el reinicio.
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
# apt install nvidia-driver nvidia-settings
 ```

```bash
dkms-status
 ```
