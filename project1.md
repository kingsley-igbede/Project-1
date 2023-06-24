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
