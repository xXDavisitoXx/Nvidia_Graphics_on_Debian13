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
# apt install linux-headers-$(uname -r)
 ```
```bash
# apt install nvidia-driver nvidia-settings
 ```

```bash
dkms-status
 ```
