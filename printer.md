## Printer Installation

CUPS telepítése
```
sudo pacman -S cups
```
Enable & Start service
```
sudo systemctl enable --now cups.service
```
Install printer driver
```
yay -S brother-hll2340dw
```
Open Cups in browser
```
http://localhost:631
```
