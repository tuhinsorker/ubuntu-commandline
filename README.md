# Install Apache, MySQL, PHP (LAMP) Stack on Ubuntu 18.04

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

## move project folder to root directory

=> sudo mv /var/www/html/onlineexam/* /var/www/html/
