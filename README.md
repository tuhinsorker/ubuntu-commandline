<p align="center"><a href="https://github.com/tuhinsorker/ubuntu-commandline" target="_blank"><img src="lamp.png" width="400"></a></p>

### Install Apache, MySQL, PHP (LAMP) Stack on Ubuntu 20.04

## Install Apache

```bash 
sudo apt update 
```
```bash 
sudo apt install apache2
```
## Configure Firewall

```bash 
Sudo ufw allow OpenSSH
```
```bash 
Sudo ufw allow in"Apache Full"
```
```bash 
Sudo ufw enable
```
```bash 
Sudo ufw status
```

## Test Apache

```bash 
sudo service apache2 status
```
## Install MySQL

```bash 
sudo apt update
```
```bash 
sudo apt install mysql-server
```
```bash 
sudo service mysql status
```
## Create MySQL User

```bash 
Sudo mysql
```
```bash 
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
```
```bash 
GRANT ALL PRIVILEGES ON* . * TO'newuser'@'localhost';
```
```bash 
FLUSHPRIVILEGES;
```
## Alter user

```bash 
ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'password';
```
## Check user

```bash 
mysql>SELECT user,authentication_string,plugin,host FROM mysql.user;
```

## Install PHP

```bash 
sudo apt update
```
```bash
sudo apt-get install -y php8.1-cli php8.1-common php8.1-mysql php8.1-zip php8.1-gd php8.1-mbstring php8.1-curl php8.1-xml php8.1-bcmath libapache2-mod-php8.1
```
- [This command will install the following modules]:

php8.1-cli - command interpreter, useful for testing PHP scripts from a shell or performing general shell scripting tasks

- [php8.1-common - documentation, examples, and common modules for PHP]
- [php8.1-mysql - for working with MySQL databases]
- [php8.1-zip - for working with compressed files]
- [php8.1-gd - for working with images]
- [php8.1-mbstring - used to manage non-ASCII strings]
- [php8.1-curl - lets you make HTTP requests in PHP]
- [php8.1-xml - for working with XML data]
- [php8.1-bcmath - used when working with precision floats]


## Installing phpMyAdmin

```bash
sudo apt update 
```

```bash
sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl
```
```bash
sudo phpenmod mbstring
```
```bash
sudo a2enconf phpmyadmin.conf
```
```bash
sudo service apache2 reload
```
```bash
sudo systemctl restart apache2
```

## Enable .htaacess

```bash
sudo a2enmod rewrite
```
```bash
sudo systemctl restart apache2
```
```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```
```bash
<Directory /var/www/html>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Require all granted
</Directory>
```
```bash
sudo systemctl restart apache2
```
## move project folder to root directory
```bash
sudo mv /var/www/html/projectfolder/* /var/www/html/
```
