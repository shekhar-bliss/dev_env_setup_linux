# Setup - LAMP

$ = Non Root User

&#35; = Root User

#### Setup LAMP on Linux machine.
1. Update System/Linux machine
```
$ sudo apt update
```

2. Install Apache2
```
$ sudo apt install apache2
$ sudo service apache2 status
```

3. Install MySQL
```
$ sudo apt install mysql-server
$ sudo mysql_secure_installation
$ sudo service mysql status
```

4. Install PHP
```
$ sudo apt install php libapache2-mod-php php-mysql

$ sudo nano /etc/apache2/mods-enabled/dir.conf

$ sudo systemctl restart apache2
$ sudo systemctl status apache2


$ sudo nano /var/www/html/info.php
$ sudo service apache2 restart

$ sudo apt search php- | less
$ sudo apt show php-cli
```
----------------------------------------------------------------
