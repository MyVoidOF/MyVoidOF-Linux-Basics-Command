# File Permissions

## Linux File Ownership

Setiap file dan direktori di sistem Unix/Linux Anda diberi 3 tipe pemilik, seperti di bawah ini.

* **Pengguna:** pengguna adalah pemilik file. Secara default, orang yang membuat file menjadi pemiliknya. Karenanya, pengguna juga terkadang disebut pemilik.
* **Grup:** grup pengguna dapat berisi beberapa pengguna. Semua pengguna yang termasuk dalam grup akan memiliki akses izin grup Linux yang sama ke file tersebut.
* **Lainnya:** pengguna lain yang memiliki akses ke file. Orang ini tidak membuat file tersebut, atau dia termasuk dalam grup pengguna yang dapat memiliki file tersebut. Secara praktis, itu berarti orang lain.

***

## Linux File Permissions

Setiap file dan direktori di sistem UNIX/Linux Anda memiliki 3 izin berikut yang ditentukan untuk semua 3 pemilik yang dibahas di atas.

* **Read:** Izin ini memberi Anda wewenang untuk membuka dan membaca file. Izin baca pada direktori memberi Anda kemampuan untuk membuat daftar kontennya.
* **Write:** Izin tulis memberi Anda wewenang untuk mengubah konten file. Izin tulis pada direktori memberi Anda wewenang untuk menambah, menghapus, dan mengganti nama file yang disimpan di direktori. Pertimbangkan skenario di mana Anda harus menulis izin pada file tetapi tidak memiliki izin menulis pada direktori tempat file disimpan. Anda akan dapat mengubah isi file. Tetapi Anda tidak akan dapat mengganti nama, memindahkan, atau menghapus file dari direktori.
* **Execute:** Di Windows, program yang dapat dieksekusi biasanya memiliki ekstensi ".exe" dan dapat Anda jalankan dengan mudah. Di Unix/Linux, Anda tidak dapat menjalankan program kecuali izin eksekusi diatur. Jika izin eksekusi tidak disetel, Anda mungkin masih dapat melihat/memodifikasi kode program (asalkan izin baca & tulis disetel), tetapi tidak menjalankannya.

Mari kita lihat izin file di Linux dengan contohnya `ls -l` command:

``` console
zold@Zold:~/linux-admin1$ ls -l
total 92
-rw-rw-r-- 1 zold devops  1377 Jun 14 16:10 'File Permissions.md'
```

Di sini, kami telah menyoroti '-rw-rw-r--' dan kode yang terlihat aneh ini adalah kode yang memberi tahu kami tentang izin Unix yang diberikan kepada pemilik, grup pengguna, dan dunia.

Di sini, '–' pertama menunjukkan jenis file

| key | Type
| --- | ----
| -   | File
| d   | Directory
| l   | Link [Shortcut]
| c   | Special File [Such as files in /dev/]
| s   | Socket
| p   | Pipe

The characters are pretty easy to remember.

* `r` read = 4
* `w` write = 2
* `x` execute = 1
* `-` No Permission = 0
* `u` user → first 3 letters
* `g` group → second 3 letters
* `o` others → last 3 letters

Mari kita lihat dengan cara ini.

Bagian pertama dari kode adalah 'rw-'. Ini menunjukkan bahwa pemilik 'zold' dapat:

* Read the file
* Write or edit the file
* He cannot execute the file since the execute bit is set to '-'.

Secara desain, banyak distribusi Linux seperti Fedora, CentOS, Ubuntu, dll. Akan menambahkan pengguna ke grup dengan nama grup yang sama dengan nama pengguna. Jadi, pengguna 'zold' ditambahkan ke grup bernama 'devops'.

Bagian kedua adalah 'rw-'. Ini untuk grup pengguna 'devops' dan anggota grup dapat:

* Read the file
* Write or edit the file

Bagian ketiga adalah untuk dunia yang berarti setiap pengguna. Dikatakan 'r–-'. Ini berarti pengguna hanya dapat:

* Read the file

***

## Change Owners

* `chown <user>.<group> <file>` mengubah pengguna dan pemilik grup file
* `chown -R <user>.<group> <directory>` mengubah pengguna dan pemilik grup direktori
* `chown <user> <file>` ubah pemilik pengguna saja
* `chgrp <group> <file>` Ubah pemilik grup saja

**Note:** For debian use `:` instead of `.`

**Example:** `chown zold:devops script.sh`

## Change Permissions

Kita bisa menggunakan perintah 'chmod' yang merupakan singkatan dari 'change mode'. Dengan menggunakan perintah, kita dapat mengatur izin (baca, tulis, eksekusi) pada file/direktori untuk pemilik, grup, dan dunia.

Untuk mengubah izin

* `+` Add
* `-` Minus
* `=` Set

Examples:

* `chmod g+w <file>` tambahkan izin menulis untuk grup
* `chmod -rx <file>` hapus baca & jalankan untuk semua [pengguna, grup, lainnya]
* `chmod 750 <file>` tambahkan izin dengan angka

[Next: Package Management](./Package%20Management.md)

[Prev: User and Groups](./User%20and%20Groups.md)
