# kali-vm
My config for a Kali VM.

## Update packages.

```sh
sudo apt update && \
sudo apt upgrade -y && \
sudo apt autoremove -y && \
sudo apt autoclean -y
```

<br />

## Create folder structure.

```sh
mkdir ~/Flo ~/Flo/Dev ~/Flo/Downloads ~/Flo/Apps ~/Flo/Dotfiles && \
rm -rf ~/Videos ~/Templates ~/Public ~/Pictures ~/Music ~/Downloads ~/Documents
```

<br />

## Install dependencies.

```sh
sudo apt update && \
sudo apt upgrade -y && \
sudo apt install -y git zsh zsh-syntax-highlighting curl \
tree ripgrep fd-find silversearcher-ag unzip bat python3-dev \
neofetch stow zoxide python3-pip libsqlite3-dev \
libssl-dev wget poppler-utils libimage-exiftool-perl && \
sudo apt autoremove -y && \
sudo apt autoclean -y
```

<br />

## Install OH-MY-ZSH.

```sh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Close terminal.<br />
Logout then login.<br />
Open terminal.

Create needed folder and files, install custom theme `ys-flo.zsh-theme` and install plugins `zsh-autosuggestions` and `zsh-syntax-highlighting`.<br />
https://github.com/Flo-Slv/Dotfiles/blob/main/oh-my-zsh/ys-flo.zsh-theme<br />
https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh<br />
https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md

```sh
mkdir -p ~/Flo/Dotfiles/oh-my-zsh && \
wget -P ~/.oh-my-zsh/custom/themes https://raw.githubusercontent.com/Flo-Slv/Dotfiles/main/oh-my-zsh/ys-flo.zsh-theme && \
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions && \
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
mv ~/.oh-my-zsh ~/Flo/Dotfiles/oh-my-zsh && \
cd ~/Flo/Dotfiles && \
stow -t ~/ oh-my-zsh
```

<br />

## Remove Vim.

```sh
sudo apt remove -y vim && \
sudo apt remove -y vim-common && \
sudo apt autoremove -y && \
sudo apt autoclean -y && \
sudo rm -rf /usr/share/vim && \
sudo rm -rf /etc/vim
```

<br />

## Install Neovim from sources.

1. Install dependencies.
```sh
cd ~ && \
sudo apt install -y ninja-build gettext libtool libtool-bin autoconf python3-dev \
automake cmake g++ pkg-config doxygen libicu-dev libboost-all-dev libssl-dev \
ripgrep fd-find silversearcher-ag zoxide python3-pip libsqlite3-dev bat
```

<br />

2. Clone Neovim repository.
```sh
git clone https://github.com/neovim/neovim ~/Flo/Apps/Neovim
```

<br />

3. Compile sources.
```sh
cd ~/Flo/Apps/Neovim && \
make CMAKE_BUILD_TYPE=RelWithDebInfo && \
sudo make install
```

## 
