# Install Apache, MySQL, PHP (LAMP) Stack on Ubuntu 18.04
An API wrapper for DigitalOcean's Spaces object storage designed for easy use. 

### Install Apache

sudo apt update 

sudo apt install apache2

### Configure Firewall

Sudo ufw allow OpenSSH

Sudo ufw allow in"Apache Full"

Sudo ufw enable

Sudo ufw status


### Test Apache

sudo service apache2 status

### Install MySQL

sudo apt update
sudo apt install mysql-server
sudo service mysql status

