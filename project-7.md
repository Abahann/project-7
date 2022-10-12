## DEVOPS TOOLING WEBSITE SOLUTION

# Step 1 - Preparing of NFS Server
>`lsbkl`
![lsblk status](./images.md/lsblk.png)

>`sudo yum install lvm2 -y`
![lvm2 status](./images.md/lvm2%20status.png)

>`sudo lvmdiskscan`
![diskscan status](./images.md/diskscan%20status.png)

> `sudo pvcreate`
![pvs status](./images.md/pvs%20status.png)

> `sudo lvcreate`
![lvs status](./images.md/lvs%20status.png)

>`sudo vgcreate`
![vgs status](./images.md/vgs%20status.png)

> ` sudo mkfs -t xfs /dev/webdata-vg/lv-apps`
![mkfs status](./images.md/mkfs%20status.png)

>`sudo mkdir /mnt/apps`
 
>`sudo mkdir /mnt/logs`
 
>`sudo mkdir /mnt/opt`
 
>`sudo mount /dev/webdata-vg/lv-apps /mnt/apps`
 
>`sudo mount /dev/webdata-vg/lv-apps /mnt/logs`
 
> `sudo mount /dev/webdata-vg/lv-apps /mnt/opt`

> `sudo yum -y update`
![yum -y update status](./images.md/yum%20-y%20update%20status.png)

>`sudo yum install nfs-utils -y`
![nfs-utils status](./images.md/nfs-utils%20status.png)

> ` sudo systemctl start nfs-server.service`
![nfs server status](./images.md/nfs%20server%20status.png)

> ` sudo chown -R nobody: /mnt/apps`

> `sudo chown -R nobody: /mnt/logs`

> `sudo chown -R nobody: /mnt/opt`

> `sudo chmod -R 777 /mnt/apps`

> `sudo chmod -R 777 /mnt/logs`

> ` sudo chmod -R 777 /mnt/opt`
![chown status](./images.md/chown%20status.png)

> ` sudo vi /etc/exports`

> ` sudo exportfs -arv`
![export status](./images.md/export%20satus.png)

## STEP 2 — CONFIGURE THE DATABASE SERVER

> `Commands:`

> ` sudo apt install mysql-server`
![mysql server status](./images.md/mysql%20server%20status.png)

> `sudo apt update`
![apt update status](./images.md/apt%20update%20status.png)

> `sudo apt install mysql- server -y`
![mysql server -y status](./images.md/mysql%20server%20-y%20status.png)

> `sudo mysql`
![mysql status](./images.md/mysql%20status.png)
![database status](./images.md/database%20status.png)

> ``

> ` sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

> ` sudo systemctl restart mysql`

> ` sudo systemctl status mysql`
![mysqld.cnf status](./images.md/mysqld.cnf%20status.png)

![conf database status](./images.md/conf%20database%20status.png)

## STEP 3 - Preparing the Web Servers

> `Commands:`

> `sudo yum install nfs-utils nfs4-acl-tools -y`
![nfs4 status](./images.md/nfs4%20status.png)

> `sudo mkdir /var/www`
![sudo var status](./images.md/sudo%20var%20status.png)


> `sudo mount -t nfs -o rw,nosuid <NFS-Server-Private-IP-Address>:/mnt/apps /var/www`
![sudo var status](./images.md/sudo%20var%20status.png)

> `sudo vi /etc/fstab`

> `sudo yum install httpd -y`
![install httpd status](./images.md/install%20httpd%20status.png)

> `sudo yum intstall git`
![git status](./images.md/git%20status.png)
![git clone status](./images.md/git%20clone%20status.png)

> `sudo yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm -y`
![rpm status](./images.md/rpm%20status.png)

> `sudo yum install yum-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm`
![yum utils status](./images.md/yum%20utils%20status.png)

> `sudo yum module reset php`
![reset php status](./images.md/reset%20php%20status.png)

> `sudo yum module enable php:remi-7.4`
![enable php status](./images.md/enable%20php%20status.png)

> `sudo yum install php php-opcache php-gd php-curl php-mysqlnd`
![yum install php](./images.md/yum%20install%20php.png)

> `sudo systemctl start php-fpm`
![php-fpm status](./images.md/php-fpm%20status.png)

> `setsebool -P httpd_execmem 1`
![test page status](./images.md/test%20page%20status.png)
![web status](./images.md/web%20status.png)
![web page1](./images.md/web%20page1.png)
![web page2](./images.md/web%20page%202.png)



















