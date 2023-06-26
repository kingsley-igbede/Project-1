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

