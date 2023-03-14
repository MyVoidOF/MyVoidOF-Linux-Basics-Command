# Best Practices

## Security Best Practices for Linux Servers

* Gunakan SSH alih-alih kata sandi untuk masuk ke server
* Jika entah bagaimana itu tidak memungkinkan, gunakan kata sandi yang kuat dan unik:
  * Kata sandi yang sama tidak boleh digunakan untuk banyak pengguna atau sistem perangkat lunak
  * Konfigurasikan kedaluwarsa, untuk memperbarui kata sandi secara teratur
  * Gunakan pengelola kata sandi untuk autentikasi dua faktor, pembuatan kata sandi, penyimpanan kata sandi cloud, dll.
* Perbarui perangkat lunak Anda secara teratur atau aktifkan pembaruan otomatis
* Hindari perangkat lunak yang tidak perlu, karena setiap perangkat lunak baru dapat mengekspos server ke potensi masalah
* Cadangkan data Anda secara teratur. Aplikasi "rsync" adalah opsi populer di Linux

***

## Users & Permissions

* Hanya gunakan akun root untuk administrasi sistem. Login dengan pengguna normal dan su untuk root
* Hapus atau kunci akun pengguna yang tidak diperlukan lagi
* Pastikan kata sandi pada akun aktif diubah secara teratur
* Kunci Akun Pengguna setelah sejumlah upaya login yang gagal

***

## Networking

* Selalu memiliki Firewall
* Batasi akses jaringan sebanyak mungkin
  * Port, yang tidak Anda perlukan harus ditutup

***

## SSH

* SSH, seperti semua layanan jaringan, harus dinonaktifkan jika tidak diperlukan
* Nonaktifkan login root melalui SSH
  * Dapat dikonfigurasi di sini: `/etc/ssh/sshd_config`
  * Login dengan user biasa dan su untuk root

[Prev: SSH](./SSH.md)
