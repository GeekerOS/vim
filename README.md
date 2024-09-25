🐸 Personal Vim8 Configs
=====================

Before installation, backup and clean all files and directories starting with '.vim' in the HOME directory to avoid effects related to the old and new configurations.

Recommended OS is CentOS 8 which have Clang 11+, GCC 7+/8+, and you also could install universal ctags(https://github.com/universal-ctags/ctags) by yourself for more ctag features.

You should compile the YCM(https://github.com/ycm-core/YouCompleteMe?tab=readme-ov-file#linux-64-bit) by yourself for C/C++.

Build Python 3.11(YCM need the python 3.8.0+)
```
sudo dnf install dnf-plugins-core  # install this to use 'dnf builddep'
sudo dnf builddep python3

wget https://www.python.org/ftp/python/3.11.10/Python-3.11.10.tgz
tar -zvxf Python-3.11.10.tgz
cd Python-3.11.10
./configure --enable-shared --enable-optimizations --with-ensurepip=install --with-lto=full
```

Build Vim
```
git clone https://github.com/vim/vim.git
cd vim
./configure --enable-python3interp=yes --with-python3-config-dir=$(python3-config --configdir)
make
sudo make install
```

**👀 Install:**

Run the command to install and config your vim shit ~

```sh
sudo wget -O - https://raw.githubusercontent.com/ylgeeker/vim/master/install.sh | sh
cd ~/.vim/plugged/YouCompleteMe
python3.11 install.py  --force-sudo --all --verbose
```

**🌈 Others:**

![avatar](https://cloud.githubusercontent.com/assets/10374559/23341312/1961f416-fc45-11e6-83ba-d7180c5fdd6d.png)

🍔 Recommended Theme: https://github.com/altercation/vim-colors-solarized

```sh
let g:solarized_termcolors=256
let g:solarized_termcolors=16
let g:solarized_termtrans=1
```

🍺 Recommended Color:

```sh
Foreground: 00f900
Background: 002b36
```

🍟 Recommended Terminal:

```sh
export PS1='\[\e[32;1m\][\u@\h \W]\\$> \[\e[0m\]'
```
