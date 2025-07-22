Termux-AllinOne/
├── install.sh
├── README.md
├── tools/
│   ├── cek_penipu.sh
│   ├── kamera_detector.sh
│   ├── scanner_jaringan.sh
│   ├── fake_hack.sh
├── setup/
│   ├── termux-banner.txt
│   └── warna-termux.sh
└── config/
    └── telegram.conf
    #!/bin/bash
echo -e "\033[1;32m[+] Memulai instalasi tools...\033[0m"
pkg update -y && pkg upgrade -y
pkg install git python nmap tsu net-tools -y

# Menyalin banner dan warna
cat setup/termux-banner.txt > $PREFIX/etc/motd
bash setup/warna-termux.sh

# Membuat alias ke ~/.bashrc
echo "alias cekpenipu='bash $HOME/Termux-AllinOne/tools/cek_penipu.sh'" >> ~/.bashrc
echo "alias hackshow='bash $HOME/Termux-AllinOne/tools/fake_hack.sh'" >> ~/.bashrc
source ~/.bashrc

echo -e "\033[1;32m[✓] Semua tools berhasil dipasang!\033[0m"
