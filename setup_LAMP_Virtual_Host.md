# Setup - LAMP - Virtual Host

$ = Non Root User

&#35; = Root User


1. Create the Directory Structure
```
$ sudo mkdir -p /var/www/example.local/public_html
```

2. Grant Permissions
```
$ sudo chown -R $USER:www-data /var/www/example.local/public_html
```

3.
```
$ sudo chmod -R 755 /var/www
```

4.  Create Demo Pages for Virtual Host
```
$ vi /var/www/example.local/public_html/index.html
```

5. Create New Virtual Host Files
```
$ sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/example.local.conf
```

6.
```
$ sudo vi /etc/apache2/sites-available/example.local.conf

<VirtualHost *:80>
    ServerAdmin admin@example.local
    ServerName example.local
    ServerAlias www.example.local
    DocumentRoot /var/www/example.local/public_html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

7. Enable the New Virtual Host Files
```
$ sudo a2ensite example.local.conf
```

8.
```
$ sudo service apache2 restart
```

9. Set Up Local Hosts File
```
$ sudo vi /etc/hosts

127.0.1.1   example.local
```


----------------------------------------------------------------
