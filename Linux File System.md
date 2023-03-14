# Linux File System

``` console
zold@Zold:~$ cd /
zold@Zold:/$ ls
bin   dev  home  lib    lib64   lost+found  mnt  proc  run   snap  sys  usr
boot  etc  init  lib32  libx32  media       opt  root  sbin  srv   tmp  var
```

* `/` root directory
* `/home` direktori home untuk semua pengguna non-root
* `/root` direktori home untuk semua pengguna root
* `/bin` file yang dapat dieksekusi pengguna misalnya: [cp, cat, ...]
* `/sbin` file sistem biner. Ini adalah executable yang digunakan untuk administrasi sistem, hanya pengguna root yang dapat menggunakan ini
* `/lib` Berisi file pustaka bersama yang diperlukan untuk mem-boot sistem dari `/bin` dan `/sbin`.
* `/usr` Ini adalah file read-only yang dapat dibagikan, termasuk binari dan pustaka yang dapat dieksekusi, file man, dan jenis dokumentasi lainnya.  
  * `/usr/local` perpustakaan dan paket yang akan Anda unduh akan ada di sini mis: buruh pelabuhan, java, ... dll
    * `/usr/local/bin` perintah paket akan ada di sini
    * `/usr/local/lib` paket akan ada di sini
* `/opt` perpustakaan dan paket yang akan Anda unduh juga akan ada di sini
  * apa perbedaan antara `/opt` dan `/usr/local`? `/opt` ada di sini paket yang tidak membagi komponennya tidak seperti `/usr/local`
* `/boot` berisi bootloader statis dan kernel yang dapat dieksekusi dan file konfigurasi yang diperlukan untuk mem-boot komputer Linux.
* `/etc` berisi file konfigurasi sistem lokal untuk komputer host.
* `/dev` berisi file perangkat untuk setiap perangkat keras yang terpasang pada sistem, mis: keyboard, mouse, kamera ... dll
* `/var` File data variabel disimpan di sini. Ini dapat mencakup hal-hal seperti file log, MySQL, file data server web, kotak masuk email .... dll
  * misalnya `/var/cache` berisi data cache dari paket
* `/tmp` direktori sementara. digunakan oleh sistem operasi dan banyak program untuk menyimpan file sementara.
* `/media` dan `/mnt` mountpoint sementara untuk sistem file biasa (seperti pada media yang tidak dapat dipindahkan) yang dapat digunakan saat administrator sedang memperbaiki atau mengerjakan sistem file.

[Next: Files and Directories](./Files%20and%20Directories.md)

[Prev: Linux Paths](./Linux%20Paths.md)
