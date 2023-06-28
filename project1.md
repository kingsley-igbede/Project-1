## Kingsley Documentation of Project 1

`sudo apt update`

`sudo apt install apache2`

`sudo systemctl status apache2`

![apache status](.\images\apache-status.PNG)


### Installing MySql

`sudo apt install mysql-server`

`sudo mysql`

![mysql status](.\images\mysql-status.PNG)


### Securing MySql

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`
`mysql> exit`

`sudo mysql_secure_installation`

`sudo mysql -p`

`mysql> exit`

![mysql security](.\images\securing-mysql.PNG)


### Installing PHP And It's Dependencies

`sudo apt install php libapache2-mod-php php-mysql`

`php -v`

![PHP install](.\images\installing-PHP.PNG)


### Virtual Host Using Apache

`sudo mkdir /var/www/projectlamp`

`sudo chown -R $USER:$USER /var/www/projectlamp`

`sudo vi /etc/apache2/sites-available/projectlamp.conf`

`<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>`

`sudo ls /etc/apache2/sites-available`

![apache virtual host](.\images\virtual-host-apache.PNG)

![apache virtual host2](.\images\virtual-host-apache2.PNG)

`sudo apache2ctl configtest`

`sudo systemctl reload apache2`

`sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`

`http://<Public-IP-Address>:80`

`http://<Public-DNS-Name>:80`

![reload apache](.\images\apache-reloaded.PNG)

![website URL1](.\images\website-url-ip-address.PNG)

![website URL2](.\images\website-url-public-dns.PNG)


### Enabling PHP On The Webseite

`sudo vim /etc/apache2/mods-enabled/dir.conf`

`<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>`

`sudo systemctl reload apache2`

`vim /var/www/projectlamp/index.php`

`<?php
phpinfo();`

![enable PHP](.\images\enable-php-website.PNG)

![enable PHP2](.\images\enable-php-website2.PNG)



