
## translate-shell
```shell
git clone https://github.com/soimort/translate-shell
cd translate-shell/
make
sudo make install
```
https://github.com/soimort/translate-shell/blob/develop/README.md

## xdg-open
### get a file's MIME type
```shell
xdg-mime query filetype hoge.*
```
### get the default applicatoin for a MIME type
```shell
xdg-mime query default image/jpeg
```
### change the default application for a MIME type
```shell
xdg-mime default xpdf.desktop application/pdf
```
https://wiki.archlinux.org/index.php/Xdg-utils#xdg-open
https://qiita.com/apu4se/items/ff7efd8d351e09bb9b54

### misc
```shell
xdg-mime default chromium.desktop x-scheme-handler/http
xdg-mime default chromium.desktop x-scheme-handler/https
```

## hyperestraier
```shell
sudo apt install ./libestraier8_1.4.13-14+b5_amd64.deb
sudo apt install ./libestraier-dev_1.4.13-14+b5_amd64.deb
sudo apt install ./hyperestraier_1.4.13-14+b5_amd64.deb
```

## alsamixer
### set the defalut soundcard
```shell
cat /proc/asound/cards
```
```
 0 [HDMI           ]: HDA-Intel - HDA Intel HDMI
                      HDA Intel HDMI at 0xf1130000 irq 54
 1 [PCH            ]: HDA-Intel - HDA Intel PCH
                      HDA Intel PCH at 0xf1134000 irq 44
```
create `/etc/asound.conf` with following
```
defaults.pcm.card 1
defaults.ctl.card 1
```


## epwing
```shell
sudo apt install lookup-el eblook
```
add the following lines to `.emacs`
```lisp
(setq lookup-enable-splash nil)
(autoload 'lookup "lookup" nil t)
(autoload 'lookup-region "lookup" nil t)
(autoload 'lookup-pattern "lookup" nil t)
(global-set-key "\C-c\C-l" 'lookup)
(global-set-key "\C-cy" 'lookup-region)
(global-set-key "\C-c\C-y" 'lookup-pattern)
(setq lookup-search-agents
      '(
        (ndeb "~/var/dict/epwing")
      ))
(setq lookup-default-dictionary-options
      '((:stemmer .  stem-english)))
(setq lookup-use-kakasi nil)
```
