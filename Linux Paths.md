# Linux Paths

## What is a path?

Jalur adalah lokasi unik ke file atau folder dalam sistem file OS. Path ke file adalah kombinasi dari / dan karakter alfanumerik.

***

## What is an absolute path?

Jalur absolut didefinisikan sebagai menentukan lokasi file atau direktori dari direktori root (/). Dengan kata lain kita dapat mengatakan jalur absolut adalah jalur lengkap dari awal sistem file aktual dari / direktori.

Beberapa contoh jalur absolut path:

* /home/imran/linux-practices/
* /var/ftp/pub
* /etc/samba.smb.conf
* /boot/grub/grub.conf

> If you see all these paths started from / directory which is a root directory for every Linux/Unix machines.

***

## What is the relative path?

Jalur relatif didefinisikan sebagai jalur yang terkait dengan direktori kerja saat ini (pwd). Misalkan saya berada di /home/zold dan saya ingin mengubah direktori ke /home/zold/linux-basics. Saya dapat menggunakan konsep jalur relatif untuk mengubah direktori ke linux-basics dan juga direktori devopsdir.

``` console
zold@Zold:~$ pwd
/home/zold
zold@Zold:~$ cd linux-basics
zold@Zold:~/linux-basics$ ls
 devopsdir
zold@Zold:~/linux-basics$ pwd
/home/zold/linux-basics
zold@Zold:~/linux-basics$ cd devopsdir
zold@Zold:~/linux-basics/devopsdir$ pwd
/home/zold/linux-basics/devopsdir
```

> If you see all these paths did not start with / directory.

[Next: Linux File System](./Linux%20File%20System.md)

[Prev: Terminal Basics](./Terminal%20Basics.md)
