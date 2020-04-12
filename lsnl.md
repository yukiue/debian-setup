## proxy
```shell
export http_proxy=http://proxy.ksc.kwansei.ac.jp:8080
export https_proxy=http://proxy.ksc.kwansei.ac.jp:8080
export ftp_proxy=http://proxy.ksc.kwansei.ac.jp:8080
```

## xpywm

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

```shell
sudo pip3 install xpywm xpymon xpylog
```

add the following lines to `~/.xinitrc`
```shell
xpywm 2>/tmp/xpywm.log &
xpymon 2>/tmp/xwpymon.log &
xpylog 2>/tmp/xpylog.log &
```

## sendscreen
```shell
sudo pip3 install sendscreen
```
