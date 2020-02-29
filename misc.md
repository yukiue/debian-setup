## translate-shell
```
$ git clone https://github.com/soimort/translate-shell
$ cd translate-shell/
$ make
$ [sudo] make install
```
https://github.com/soimort/translate-shell/blob/develop/README.md

## xdg-open
### get a file's MIME type
```
$ xdg-mime query filetype hoge.*
```
### get the default applicatoin for a MIME type
```
$ xdg-mime query default image/jpeg
```
### change the default application for a MIME type
```
$ xdg-mime default xpdf.desktop application/pdf
```
https://wiki.archlinux.org/index.php/Xdg-utils#xdg-open
https://qiita.com/apu4se/items/ff7efd8d351e09bb9b54
