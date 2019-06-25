owncloud :

Database mysql :
user : ownclouds
pass : smkn12019

login owncloud page :
user : idris
pass : smkn12019


===============================================================
===============================================================

Pastikan LAMP sudah terinstall :
- Linux
- Apache2
- mysql
- PHP (gunakan php versi 5.6)

===============================================================

Dump Vhost Apache2 :
sudo apache2ctl -t -D DUMP_VHOSTS | grep server_domain_or_IP
sudo apache2ctl -t -D DUMP_VHOSTS | grep localhost / 127.0.0.1

output :
*:443                  server_domain_or_IP (/etc/apache2/sites-enabled/server_domain_or_IP-le-ssl.conf:2)
         port 80 namevhost server_domain_or_IP (/etc/apache2/sites-enabled/server_domain_or_IP.conf:1)

===============================================================

add repository owncloud v10 :
echo 'deb http://download.owncloud.org/download/repositories/10.0/Ubuntu_18.04/ /' | sudo tee /etc/apt/sources.list.d/owncloud.list

===============================================================

Refresh repository :
sudo apt-get update

===============================================================

add module php dan owncloud :
- php-bz2
- php-curl
- php-gd
- php-imagick
- php-intl
- php-mbstring
- php-xml
- php-zip

`sudo apt-get install php-bz2 php-curl php-gd php-imagick php-intl php-mbstring php-xml php-zip owncloud-files`

===============================================================

Add Document Root Apache :

(Edit di directory /etc/apache2/site-available/000-default.conf)

<VirtualHost *:80>
    . . .
    DocumentRoot /var/www/owncloud
    . . .
</VirtualHost>

===============================================================

Check syntax apache error atau tidak :
sudo apache2ctl configtest

===============================================================

Reload / restart service apache2 :

sudo systemctl restart apache2 / sudo systemctl reload apache2

===============================================================

