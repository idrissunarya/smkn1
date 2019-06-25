## Data Owncloud

## Database mysql
| __User__ | __Password__ |
|----------|--------------|
| owncloud | `smkn12019` |

## Login page Owncloud 
| __User__ | __Password__ |
|----------|--------------|
| idris | `smkn12019` |
| guru01 | `rahasia` |

## Pastikan LAMP sudah terinstall :
- Linux
- Apache2
- mysql
- PHP (gunakan php versi 5.6)

===============================================================

## Dump Vhost Apache2 :
```yaml
sudo apache2ctl -t -D DUMP_VHOSTS | grep server_domain_or_IP
```

```yaml
sudo apache2ctl -t -D DUMP_VHOSTS | grep localhost / 127.0.0.1
```

> output :
*:443                  server_domain_or_IP (/etc/apache2/sites-enabled/server_domain_or_IP-le-ssl.conf:2)
         port 80 namevhost server_domain_or_IP (/etc/apache2/sites-enabled/server_domain_or_IP.conf:1)



## Add repository owncloud v10 :
```yaml
echo 'deb http://download.owncloud.org/download/repositories/10.0/Ubuntu_18.04/ /' | sudo tee /etc/apt/sources.list.d/owncloud.list
```

## Add repository owncloud v9 (ubuntu 16.04)
```yaml
echo 'deb https://download.owncloud.org/download/repositories/stable/Ubuntu_16.04/ /' | sudo tee /etc/apt/sources.list.d/owncloud.list
```


## Refresh repository :
```yaml
sudo apt-get update
```

## Add module php dan owncloud :
- php5.6-bz2
- php5.6-curl
- php5.6-gd
- php5.6-imagick
- php5.6-intl
- php5.6-mbstring
- php5.6-xml
- php5.6-zip
- `owncloud-files`

```yaml
sudo apt-get install php5.6-bz2 php5.6-curl php5.6-gd php5.6-imagick php5.6-intl php5.6-mbstring php5.6-xml php5.6-zip owncloud-files
```


## Add Document Root Apache :

> (Edit di directory /etc/apache2/site-available/000-default.conf)

```yaml
<VirtualHost *:80>
    . . .
    DocumentRoot /var/www/owncloud
    . . .
</VirtualHost>
```


## Check syntax apache error atau tidak :
```yaml
sudo apache2ctl configtest
```


## Reload / restart service apache2 :
```yaml
sudo systemctl restart apache2 / sudo systemctl reload apache2
```

## Configue Database Mysql 

```yaml
sudo mysql -u root -p
```

## create database owncloud
```yaml
mysql> create database owncloud
```

## Set privileges and user password
```yaml
mysql> GRANT ALL ON owncloud.* to 'owncloud'@'localhost' IDENTIFIED BY 'password_anda';
```

```yaml
msql> FLUSH PRIVILEGES;
```

```yaml
mysql> exit;
```



