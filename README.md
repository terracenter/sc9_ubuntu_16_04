Servidor WEB Apahe
aptitude install apache2

PHP 7.0
apttitude install php7.0 php7.0-dev php7.0-cli php-pear libapache2-mod-php7.0 php7.0-mbstring php7.0-zip

php -v
PHP 7.0.22-0ubuntu0.16.04.1 (cli) ( NTS )
Copyright (c) 1997-2017 The PHP Group
Zend Engine v3.0.0, Copyright (c) 1998-2017 Zend Technologies
    with Zend OPcache v7.0.22-0ubuntu0.16.04.1, Copyright (c) 1999-2017, by Zend Technologies


Modificacion del PHP.INI
cp /etc/php/7.0/apache2/php.ini /etc/php/7.0/apache2/php.ini.bak

vim /etc/php/7.0/apache2/php.ini
disable_functions =
date.timezone = Amercia/Caracas   ## Soy de Venezuela

service apache2 reload



ACTIVATING THE EXTENSION OF THE DATABASE:
PostgreSQL:
apt-get install php7.0-pgsql
MySQL:
apt-get install php7.0-mysql
SQLite:
apt-get install php7.0-sqlite
FireBird:
apt-get install php7.0-interbase
Odbc:
apt-get install php7.0-odbc

ACTIVATING THE GD LIBRARY
This library is necessary to render the images.

Use the command below:
apt-get install php7.0-gd

Enabling SourceGuardian Loader
cd /usr/local/src/
wget -c https://www.sourceguardian.com/loaders/download/loaders.linux-x86_64.zip
unzip loaders.linux-x86_64.zip -d loaders
Create a folder to place the file ixed.7.0.lin
sudo mkdir /usr/lib/php/sourceguardian

Copy the file ixed.7.0.lin that was downloaded according to your architecture to the folder /usr/lib/php7/sourceguardian
cp loaders/ixed.7.0.lin /usr/lib/php/sourceguardian/

Bajaar escriptcase y descomprimir
wget -c http://downloads.scriptcase.com.br/downloads/v9/packs/scriptcase-9.0.030-es_es.zip
unzip scriptcase-9.0.030-es_es.zip -d /var/www/html/

Configure the permission to Total Control for this folder:
chmod 777 -R /usr/lib/php/sourceguardian

Edit the file php.ini and add the to the end of the file the content below:
vim /etc/php/7.0/apache2/php.ini

[SourceGuardian] 
zend_extension=/usr/lib/php/sourceguardian/ixed.7.0.lin

cp /var/www/html/devel/lib/third/zend/zendid.linux64 /var/www/html/devel/lib/third/zend/zendid
chown -R www-data:www-data /var/www/html/
 chmod -R 775 /var/www/html/desarrollo/

Restart the Apache service using the command below:
service apache2 restart


 
 
