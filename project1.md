# WEB STACK IMPLEMENTATION (LEMP STACK) PROJECT 1
### Connecting to EC2 terminaL

`cd ~/Downloads`

`cd~/Downloads/backup` 

![Ubuntu server](./images/Ubuntu%20server%20.png)

### Updating SYSTEM WITH COMMANDS BELOW.
`sudo apt update`
### INSTALLNG APACHE2 SERVER 
`sudo apt install apache2`
`sudo systemctl status apache2`
![Apache2 server](./images/Apache2%20server.png)

### OPENING POST 80
'Opening Port 80'
![Port 80 opening](./images/Port%2080%20opened.png)

`curl http://localhost:80`
![Apache2 defaultpage](./images/Apache%20defaultpage.png)
### INSTALLING MYSQL SERVER WITH THE COMMANDS BELOW
`sudo apt install mysql-server`
![Sudo apt mysqlserver](./images/Sudo%20apt%20install%20mysqlserver.png)

`sudo mysql`- using this cmmad to acertain myqsl server is running properly.
`setting password to run a security script`
`sudo mysql_secure_installation`
`sudo mysql -p`
`mysql> exit`

![Mysql server](./images/Mysql%20server.png)
' setting of password to run a security script'
 
##  INSTALLING PHP
`sudo apt install php libapache2-mod-php php-mysql`
`php -v`
![Php -v](./images/Php%20-v.png)

##  CREATING A VIRTUAL HOST FOR YOUR WEBSITE USING APACHE
`sudo mkdir /var/www/projectlamp`
`sudo chown -R $USER:$USER /var/www/projectlamp`
`sudo vi /etc/apache2/sites-available/projectlamp.conf`
![Apache virtualhost](./images/apache%20virtualhost.png)

`sudo ls /etc/apache2/sites-available'
' 
`sudo a2ensite projectlamp`
`sudo apache2ctl configtest`
`sudo systemctl reload apache2`
`sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`
' ![Hello LAMP](./images/Hello%20LAMP.png)

###  ENABLING PHP ON THE WEBSITE
`sudo vim /etc/apache2/mods-enabled/dir.conf`
![php file](./images/php%20file.png)

![Enabling php](./images/Enabling%20php.png)
`sudo systemctl reload apache2`

`Creating a new file named index.php`
`vim /var/www/projectlamp/index.php`
![Php page loaded](./images/Php%20page%20loaded.png)
