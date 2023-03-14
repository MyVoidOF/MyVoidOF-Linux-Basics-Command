# Archive

kami akan menggunakan utilitas pengarsipan `tar` and `zip`

`tar` dengan sendirinya hanya menggabungkan file bersama (hasilnya disebut tarball), sementara `zip` menerapkan kompresi juga.
***

## Tar

* `tar -czvf <Tar Name> <Directory>` kompres file/direktori

``` console
root@Zold:~# ls devops
ansible  aws  kubernetes  prometheus  terraform
root@Zold:~# tar -czvf devops-tools.tar.gz devops
devops/
devops/prometheus
devops/kubernetes
devops/terraform
devops/aws
devops/ansible
```

* `tar -xzvf <Tar File>` uncompresse tar file
* `tar -xzvf <Tar File> -C <Path>` uncompresse tar file and putting the content in a specific path

``` console
root@Zold:~# ls
devops-tools.tar.gz  tools
root@Zold:~# tar -xzvf devops-tools.tar.gz -C tools
devops/
devops/prometheus
devops/kubernetes
devops/terraform
devops/aws
devops/ansible
root@Zold:~# ls tools
devops
root@Zold:~# ls tools/devops
ansible  aws  kubernetes  prometheus  terraform
```

***

## Zip

Pertama kita perlu menginstal paket `sudo apt install zip`

* `zip <Zip Name>` compresse file/empty directory
* `zip -r <Zip Name> <Directory>` compresse directory

``` console
root@Zold:~# ls devops
ansible  aws  kubernetes  prometheus  terraform
root@Zold:~# zip -r devops-package.zip devops
  adding: devops/ (stored 0%)
  adding: devops/prometheus (stored 0%)
  adding: devops/kubernetes (stored 0%)
  adding: devops/terraform (stored 0%)
  adding: devops/aws (stored 0%)
  adding: devops/ansible (stored 0%)
```

* `unzip <Zip File>` uncompresse zip file

``` console
root@Zold:~# rm -rf devops
root@Zold:~# ls
devops-package.zip
root@Zold:~# unzip devops-package.zip
Archive:  devops-package.zip
   creating: devops/
 extracting: devops/prometheus
 extracting: devops/kubernetes
 extracting: devops/terraform
 extracting: devops/aws
 extracting: devops/ansible
root@Zold:~# ls devops
ansible  aws  kubernetes  prometheus  terraform
```

[Next: Services](./Services.md)

[Prev: Redirections](./Redirections.md)
