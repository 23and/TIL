#linux open source software
- linux is growing fast, more and more additional features and fix bugs are regularly
- everyone can develop linux, many community groups create a new linux distribution, this is known as the "distro".
- proprietary platform to multi-vendor (not bound by a corporation)
- linux -> powerful, stable, low resources, no virus

- BIND
- Apache
- Proxy server(squid)
- Vsftpd
- Sendmail
- DHCP Server
- MySQL, ssh server
- samba

- command ubuntu
````
sudo apt-get update

sudo -> root
sudo apt-get install apache2 php5 php5-mysql mysql phpmyadmin
sudo apt-get install apache2 php7.0 php7.0-mysql mysql-server
sudo apt-get install vim
sudo /etc/apache2/
````
````
brew install homebrew/php/phpmyadmin
````
````
mysql -u root -p
````
````
mysqld_safe --skip-grant-tables &
````
````
sudo mv smb.conf smb.conf.ori
sudo systemctl samba start
````
````
ubuntu 16.04
````
- https://diegoe.be/2014/03/26/setting-up-apache-php-mysql-on-osx-with-homebrew/