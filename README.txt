Домашнее задание №1
Обновить ядро в базовой системе
-----------------------------
Использовал Vagrant файл вложеннный в Домашнее задание.
Комады для обновления
[vagrant@otuslinux ~]$ uname -r
3.10.0-1127.el7.x86_64
[vagrant@otuslinux ~]$ cd /boot/
[vagrant@otuslinux boot]$ ls
System.map-3.10.0-1127.el7.x86_64  initramfs-3.10.0-1127.el7.x86_64.img
config-3.10.0-1127.el7.x86_64      symvers-3.10.0-1127.el7.x86_64.gz
efi                                vmlinuz-3.10.0-1127.el7.x86_64
grub2
[vagrant@otuslinux ~]$ sudo yum update
[vagrant@otuslinux ~]$ sudo rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org
[vagrant@otuslinux ~]$ sudo yum install -y https://www.elrepo.org/elrepo-release-7.el7.elrepo.noarch.rpm 
[vagrant@otuslinux ~]$ cd /boot/
[vagrant@otuslinux boot]$ ls -l
итого 45708
-rw-r--r--. 1 root root   153562 мар 31  2020 config-3.10.0-1127.el7.x86_64
-rw-r--r--. 1 root root   153619 янв 25 16:45 config-3.10.0-1160.83.1.el7.x86_64
drwxr-xr-x. 3 root root       17 апр 30  2020 efi
drwx------. 5 root root       97 янв 28 04:05 grub2
-rw-------. 1 root root 12405333 апр 30  2020 initramfs-3.10.0-1127.el7.x86_64.img
-rw-------. 1 root root 12378873 янв 28 04:05 initramfs-3.10.0-1160.83.1.el7.x86_64.img
-rw-r--r--. 1 root root   320512 мар 31  2020 symvers-3.10.0-1127.el7.x86_64.gz
-rw-r--r--. 1 root root   320743 янв 25 16:46 symvers-3.10.0-1160.83.1.el7.x86_64.gz
-rw-------. 1 root root  3611662 мар 31  2020 System.map-3.10.0-1127.el7.x86_64
-rw-------. 1 root root  3623845 янв 25 16:45 System.map-3.10.0-1160.83.1.el7.x86_64
-rwxr-xr-x. 1 root root  6762688 мар 31  2020 vmlinuz-3.10.0-1127.el7.x86_64
-rwxr-xr-x. 1 root root  7051880 янв 25 16:45 vmlinuz-3.10.0-1160.83.1.el7.x86_64
[vagrant@otuslinux boot]$ sudo yum --enablerepo elrepo-kernel install kernel-ml -y
[vagrant@otuslinux boot]$ uname -r
3.10.0-1127.el7.x86_64
[vagrant@otuslinux boot]$ reboot
[vagrant@otuslinux ~]$ uname -r
3.10.0-1160.83.1.el7.x86_64



