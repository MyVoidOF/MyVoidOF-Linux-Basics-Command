# Filters

## Reading File

* `cat <File>` gabungkan file dan cetak pada output standar

``` console
root@Zold:~# cat myfile.script
Hello World!
This is text in file.
For testing.
```

* `less` membaca file besar halaman demi halaman atau baris demi baris
* `b` mundur satu halaman
* **SPACE** pergi ke halaman berikutnya sesuai dengan si terminal
ze
***

## Search in File

* `grep <word> <file>` mencari kata dalam file
* `grep -i <word> <file>` mencari kata kapital dalam file
* `grep -i <word> *` Cari di semua file di jalur kerja
* `grep -iR <word> *` Cari di semua file di jalur kerja dan semua direktori dengan file mereka
* `grep -v 'word'` Balikkan arti pencocokan, untuk memilih garis yang tidak cocok.
* `free -m | grep Mem` Cari kata dari output perintah lain

``` console
root@Zold:~# free -m
              total        used        free      shared  buff/cache   available
Mem:           1626         223        1279           2         123        1268
Swap:          1024           0        1024

root@Zold:~# free -m | grep Mem
Mem:           1626         223        1279           2         123        1268

root@Zold:~# free -m | grep -v Mem
              total        used        free      shared  buff/cache   available
Swap:          1024           0        1024
```

***

## Head & Tail of File

* `head <file>` Cetak 10 baris pertama dari setiap FILE
  * `head -3 <file>` Cetak 3 baris saja **ubah angka menjadi apa saja**
* `tail <file>` Cetak 10 baris terakhir dari setiap FILE
  * `tail -4 <file>` Cetak 4 baris saja **ubah nomor menjadi apa saja**
  * `tail -f <file>` keluaran data yang ditambahkan saat file tumbuh

***

## Split

* `cut -d <Delimiter> -f <Index> <File>` hapus bagian dari setiap baris file

``` console
root@Zold:~# cut -d : -f1 /etc/passwd
root
daemon
bin
sys
sync
games
man
lp
mail
news
uucp
proxy
```

***

## Replace

* `sed 's/old/new/gi' <file>` ganti kata "lama" dengan kata "baru" dalam sebuah file
* `sed -i 's/old/new/gi' <file>` ganti kata "lama" dengan kata "baru" dan edit file di tempat
* `sed -i 's/root/boot/gi' testdir/*` ganti kata di semua file dalam direktori

[Next: Redirections](./Redirections.md)

[Prev: Vim Editor](./Vim%20Editor.md)
