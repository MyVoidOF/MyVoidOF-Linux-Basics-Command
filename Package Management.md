# Package Management

Singkatnya, manajemen paket adalah metode menginstal dan memelihara (termasuk memperbarui dan mungkin juga menghapus) perangkat lunak pada sistem.

## High and low-level package tools

Untuk melakukan tugas manajemen paket secara efektif, Anda perlu menyadari bahwa Anda akan memiliki dua jenis utilitas yang tersedia: alat tingkat rendah (yang menangani penginstalan aktual, pemutakhiran, dan penghapusan file paket di backend), dan alat tingkat tinggi (yang bertanggung jawab untuk memastikan bahwa tugas resolusi ketergantungan dan pencarian metadata - "data tentang data" - dilakukan).

DISTRIBUTION           | LOW-LEVEL TOOL | HIGH-LEVEL TOOL
---------------------- | -------------- | ----------------
Debian and derivatives | dpkg           | apt-get / aptitude
CentOS                 | rpm            | yum

***

## CentOS Distribution

### yum command

* `yum update && yum upgrade` dua perintah yang dapat Anda gunakan untuk memperbarui semua paket Anda di distribusi CentOS Linux.
* `yum install <Package>` unduh & instal paket
  * `yum install <Package> -y` secara otomatis menjawab ya untuk semua pertanyaan.
* `yum remove <Package>` hapus paket yang diinstal dari sistem
* `yum search <Package>` cari di repositori yum
* `yum clean all` membersihkan cache lokal

**Example** install nginx:

* `ls /etc/yum.repos.d/` → Files info of repo
* `yum install epel-release -y`
* `yum install nginx`

### rpm command

First download the package via `wget` or `curl`

Then `rpm` commands:

* `rpm -ivh <Package Name>` install package
* `rpm -e <Package Name>` remove installed package
* `rpm -qa` all rpm packages

***

## Debian Distribution

### apt command

* `apt update && apt upgrade` dua perintah yang dapat Anda gunakan untuk memperbarui semua paket Anda di Debian atau distribusi Linux berbasis Debian.
* `apt search <Package>` cari paket di semua repositori
* `apt install <Package>` install package
  * `apt install <Package1> <Package2>` install multi packages
* `apt remove <Package>` remove installed package
  * `apt purge <Package>` remove installed package with all files

### dpkg command

First download the package via `wget` or `curl`

Then `dpkg` commands:

* `dpkg -i <Package Name>` install package
* `dpkg -r <Package Name>` remove installed package

[Next: Vim Editor](./Vim%20Editor.md)

[Prev: File Permissions](./File%20Permissions.md)
