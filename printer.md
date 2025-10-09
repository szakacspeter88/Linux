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
Select administration 
<img width="1617" height="521" alt="image" src="https://github.com/user-attachments/assets/35865f8c-4817-4607-9813-cbc75fca305e" />
