# Install Apache, MySQL, PHP (LAMP) Stack on Ubuntu 20.04

### Install Apache

=> sudo apt update 

=> sudo apt install apache2

### Configure Firewall

=> Sudo ufw allow OpenSSH

=> Sudo ufw allow in"Apache Full"

=> Sudo ufw enable

=> Sudo ufw status


### Test Apache

=> sudo service apache2 status

### Install MySQL

=> sudo apt update
=> sudo apt install mysql-server
=> sudo service mysql status

### Create MySQL User

=> Sudo mysql

=> CREATEUSER'newuser'@'localhost'IDENTIFIEDBY'password';

=> GRANT ALL PRIVILEGESON* . * TO'newuser'@'localhost';

=> FLUSHPRIVILEGES;

### Alter user

=> ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'password';

### Check user

=> mysql>SELECT user,authentication_string,plugin,host FROM mysql.user;


### Install PHP

=> sudo apt update

=> sudo apt-get install -y php8.1-cli php8.1-common php8.1-mysql php8.1-zip php8.1-gd php8.1-mbstring php8.1-curl php8.1-xml php8.1-bcmath

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

=> sudo apt update 

=> sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl

=> sudo phpenmod mbstring

=> sudo a2enconf phpmyadmin.conf

=> sudo service apache2 reload

=> sudo systemctl restart apache2


### Enable .htaacess

=> sudo a2enmod rewite

=> sudo systemctl restart apache2

=> sudo nano /etc/apache2/sites-available/000-default.conf

<Directory /var/www/html>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Require all granted
</Directory>

=> sudo systemctl restart apache2

## move project folder to root directory

=> sudo mv /var/www/html/onlineexam/* /var/www/html/
