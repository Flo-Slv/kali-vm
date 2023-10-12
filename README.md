# kali-vm
My config for a Kali VM.

```sh
sudo apt update && \
sudo apt upgrade -y && \
sudo apt autoremove -y && \
sudo apt autoclean -y
```

Create folder structure.
```sh
mkdir ~/Flo ~/Flo/Dev ~/Flo/Downloads ~/Flo/Apps ~/Flo/Dotfiles && \
rm -rf ~/Videos ~/Templates ~/Public ~/Pictures ~/Music ~/Downloads ~/Documents
```

Remove vim.
```sh
sudo apt remove -y vim && \
sudo apt remove -y vim-common && \
sudo apt autoremove -y && \
sudo apt autoclean -y && \
sudo rm -rf /usr/share/vim && \
sudo rm -rf /etc/vim
```

Install dependencies.
```sh
sudo apt update && \
sudo apt upgrade -y && \
sudo apt install -y git zsh zsh-syntax-highlighting curl i3 rofi compton \
tree ripgrep fd-find silversearcher-ag unzip bat python3-dev \
neofetch stow zoxide python3-pip libsqlite3-dev \
libssl-dev wget && \
sudo apt autoremove -y && \
sudo apt autoclean -y
```
