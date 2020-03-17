## sudo
```shell
adduser YOUR_HOSTNAME sudo
```

## keybinding
edit /etc/default/keyboard
```
XKBOPTIONS="ctrl:nocaps"
```

## zshell
```shell
chsh -s /bin/zsh
```

## wireless network
add the following lines to /etc/network/interfaces
```
auto wlp2s0
iface wlp2s0 inet dhcp
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```
add the following lines to /etc/wpa_supplicant/wpa_supplicant.conf
```
network={
    ssid="YOUR_SSID"
    psk="YOUR_PSK"
}
```

## proxy
```
export http_proxy=http://proxy.ksc.kwansei.ac.jp:8080
export https_proxy=http://proxy.ksc.kwansei.ac.jp:8080
export ftp_proxy=http://proxy.ksc.kwansei.ac.jp:8080
```

## additional packages
```shell
sudo apt install zsh fish emacs25 git tmux xsel rsync wireless-tools net-tools xorg rxvt-unicode-256color xfonts-terminus fzf chromium imagemagick alsa-utils
```
### python3
```shell
python3 python3-pip
```
### browser
```shell
chromium
```
### ps/eps/pdf
```shell
sudo apt install mupdf evince gv pdftk pdfgrep
```
### image
```shell
sudo apt install mirage eog
```
### music
```shell
sudo apt install mplayer cmus
```
### misc
```shell
gnuplot unar curl mew ffmpeg nkf graphviz tree libreoffice imagemagick xfonts-terminus
```
 
## spacemacs
```shell
git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
```

## bat
download the .deb package from the [release page](https://github.com/sharkdp/bat/releases)

```shell
sudo dpkg -i bat_0.12.1_amd64.deb
```

## Source Code Pro
```shell
wget https://github.com/adobe-fonts/source-code-pro/archive/2.030R-ro/1.050R-it.zip -P /tmp/source-code-pro
cd /tmp/source-code-pro
unzip 1.050R-it.zip
mkdir ~/.fonts
cp source-code-pro-*-it/OTF/*.otf ~/.fonts/
fc-cache -fv
```


## Mozc
```shell
sudo apt install fcitx fcitx-mozc dbus-x11
im-config
```
select "fcitx"
```shell
fcitx-configtool
```
add "mozc"

add the following lines to ~/.xinitrc
```shell
export DefaultImModule=fcitx
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
fcitx-autostart
```
Ref: https://medium.com/@h.taiju/setup-japanese-input-environment-on-debian-87768042d068

### mozc config
```
Space input style: Halfwidth
```

### mozc config tools
```shell
/usr/lib/mozc/mozc_tool --mode=config_dialog
/usr/lib/mozc/mozc_tool --mode=dictionary_tool
/usr/lib/mozc/mozc_tool --mode=word_register_dialog
/usr/lib/mozc/mozc_tool --mode=hand_writing
/usr/lib/mozc/mozc_tool --mode=character_palette
```

### emacs mozc
```shell
sudo apt install emacs-mozc
```
add the following lines to ~/.emacs
```lisp
;;mozc
(require 'mozc)
(setq default-input-method "japanese-mozc")

;;(global-set-key (kbd "C-j") 'toggle-input-method)
```

## X Window Manager
### xpywm
[xpywm](http://www.lsnl.jp/~ohsaki/software/xpywm/)
```shell
wget http://www.lsnl.jp/~ohsaki/software/xpywm/Makefile
sudo make install
make fetch-skelton
cp skel.xinitrc ~/.xinitrc
cp skel.Xdefaults ~/.Xdefaults
cp skel.emacs ~/.emacs
startx
```
### i3

[i3](https://i3wm.org/)

```shell
sudo apt install i3
echo "exec i3" >> ~/.xinitrc
```

## Mathematica

[install for linux](http://support.wolfram.com/kb/12453)

[activate](https://reference.wolfram.com/language/tutorial/ActivatingMathematica.html)

Note: It may be necessary to start Mathematica(GUI version) in order to activate.

## LaTex
```
sudo apt install texlive-full
```

## Zoom
download the .deb file from the [download page](https://zoom.us/download?os=linux)

```shell
sudo apt install ./zoom_amd64.deb
```

## Mendeley Desktop
[Installation Guide for Mendeley Desktop for Ubuntu/Debian](https://www.mendeley.com/guides/download-mendeley-desktop/ubuntu/instructions)
