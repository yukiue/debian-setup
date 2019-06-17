## keybinding(caps→ctrl)
```
$ emacs /etc/default/keyboard

XKBOPTIONS="ctrl:nocaps"
```

## wireless-networks
```
$ sudo emacs /etc/wpa_supplicant/wpa_supplicant.conf

network={
    ssid=""
    psk=""
}

$ sudo emacs /etc/network/interfaces

auto wlp2s0
iface wlp2s0 inet dhcp
wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```

## proxy
```
$ emacs ~/.zshrc
PROXY="proxy.ksc.kwansei.ac.jp:8080"
$ export http_proxy=http://$PROXY
$ export https_proxy=http://$PROXY
$ export ftp_proxy=http://$PROXY
```

## sudo
```
# visudo

hoge  ALL=(ALL:ALL) ALL
```


## mozc
```
$ sudo apt install fcitx fcitx-mozc dbus-x11
$ im-config

select "fcitx"

$ fcitx-configtool

+ mozc

$ emacs ~/.xinitrc

export DefaultImModule=fcitx
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
# https://fcitx-im.org/wiki/Configure_(Other)
# eval `dbus-launch --sh-syntax --exit-with-session`
fcitx-autostart
```
https://medium.com/@h.taiju/setup-japanese-input-environment-on-debian-87768042d068

mozc settings
```    
$ /usr/lib/mozc/mozc_tool --mode=config_dialog
$ /usr/lib/mozc/mozc_tool --mode=dictionary_tool
$ /usr/lib/mozc/mozc_tool --mode=word_register_dialog
$ /usr/lib/mozc/mozc_tool --mode=hand_writing
$ /usr/lib/mozc/mozc_tool --mode=character_palette
```

emacs mozc
```
$ sudo apt install emacs-mozc
$ emacs ~/.emacs

;;mozc
(require 'mozc)
(setq default-input-method "japanese-mozc")

;;(global-set-key (kbd "C-j") 'toggle-input-method)
```

## xpywm(window manager)

[xpywm](http://www.lsnl.jp/~ohsaki/software/xpywm/)
```
$ wget http://www.lsnl.jp/~ohsaki/software/xpywm/Makefile
# make install
$ make fetch-skelton
$ cp skel.xinitrc ~/.xinitrc
$ cp skel.Xdefaults ~/.Xdefaults
$ cp skel.emacs ~/.emacs
$ startx
```

## mathematica

[install for linux](http://support.wolfram.com/kb/12453)

[activate](https://reference.wolfram.com/language/tutorial/ActivatingMathematica.html)

Note: It may be necessary to start Mathematica(GUI version) in order to activate.

## latex
```
$ sudo apt install texlive-full
```

## translate-shell
```
$ git clone https://github.com/soimort/translate-shell
$ cd translate-shell/
$ make
$ [sudo] make install
```
https://github.com/soimort/translate-shell/blob/develop/README.md

## xdg-open
```
$ xdg-mime query filetype hoge.*

```
https://qiita.com/apu4se/items/ff7efd8d351e09bb9b54
