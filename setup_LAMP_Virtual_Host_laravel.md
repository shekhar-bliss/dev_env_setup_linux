# Setup - LAMP - Virtual Host

$ = Non Root User

&#35; = Root User


1. Create the Directory Structure
```
$ sudo mkdir -p /var/www/laravel.5.1.local/public_html
```

2. Grant Permissions
```
$ sudo chown -R $USER:www-data /var/www/laravel.5.1.local/public_html
```

3.
```
$ sudo chmod -R 755 /var/www
```

4. Create New Virtual Host Files
```
$ sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/laravel.5.1.local.conf
```

5.
```
$ sudo vi /etc/apache2/sites-available/laravel.5.1.local.conf

<VirtualHost *:80>
    ServerAdmin admin@laravel.5.1.local
    ServerName laravel.5.1.local
    ServerAlias www.laravel.5.1.local
    DocumentRoot /var/www/laravel.5.1.local/public_html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

6. Enable the New Virtual Host Files
```
$ sudo a2ensite laravel.5.1.local.conf
```

7.
```
$ sudo service apache2 restart
```

8. Set Up Local Hosts File
```
$ sudo vi /etc/hosts

127.0.1.1   laravel.5.1.local
```


8. PHP Extension
```
$ php -m
$ sudo apt install php-common php-mbstring php-xml php-zip

```

9. Enable mod_rewrite
```
$ sudo a2enmod rewrite

```

10. Installing Laravel Via Composer Create-Project
```
$ composer create-project laravel/laravel blog "5.1.*"

```

11. Directory Permissions
```
$ sudo chown -R $USER:www-data /path/to/your/laravel/root/directory

$ sudo find /path/to/your/laravel/root/directory -type f -exec chmod 644 {} \;
$ sudo find /path/to/your/laravel/root/directory -type d -exec chmod 755 {} \;

$ sudo chgrp -R www-data storage bootstrap/cache
$ sudo chmod -R ug+rwx storage bootstrap/cache

$ sudo chgrp -R www-data storage/logs
$ sudo chmod -R ug+rwx storage/logs

```

12. Naming Application
```
$ php artisan app:name Horsefly

```

13. Database Migrations
```
$ php artisan migrate

```

14. Application Key
```
$ php artisan key:generate

```


15. The Jobs Directory
```
$ php artisan key:generate

```
----------------------------------------------------------------
