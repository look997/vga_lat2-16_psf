# vga_lat2-16.psf

Domyślny font systemu, ale w postaci pliku ISO-8859-2 (ISO Latin-2), czyli z łacińskimi literami, w tym z polskimi literami. 

## Ustawienie dla Arch Linux

```bash
sudo pacman -S sed tee --noconfirm

sudo sed -e '/#pl_PL.UTF-8 UTF-8/ s/^#*//' -i /etc/locale.gen
sudo sed -e '/#pl_PL ISO-8859-2/ s/^#*//' -i /etc/locale.gen
# samo odkomentowuje z pliku /etc/locale.gen, te dwie linijki:
# #en_US.UTF-8 UTF-8, 
# #pl_PL.UTF-8 UTF-8

sudo locale-gen

sudo tee /etc/locale.conf << EOF
LANG=pl_PL.UTF-8
EOF

sudo cp vga_lat2-16.psf /usr/share/kbd/consolefonts

sudo tee /etc/vconsole.conf << EOF
KEYMAP=pl2
FONT=vga_lat2-16.psf
FONT_MAP=8859-2
EOF
```

## Nazwy fontu w oryginalnej wersji

CP437 character set  
IBM VGA 9x16  
Perfect DOS VGA 437  
default8x16  
Standard vga font
