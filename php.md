## Install PHP version 5.6 dan add repository
```yaml
sudo apt-get install python-software-properties
```
```yaml
sudo add-apt-repository ppa:ondrej/php
```
```yaml
sudo apt-get update
```
```yaml
sudo apt-get install php5.6
```

## Check php version

```yaml
php --version
```

## Check source php dalam OS 

`/etc/php/` dan `/usr/bin/php?`

## Swicth php untuk apache2

> disable php 7.0
```yaml
sudo a2dismod php7.0
```

> enable php 5.6
```yaml
sudo a2enmod php5.6
```

> restart apache2
```yaml
sudo sysytemctl restart apache2.service
```

## Set module php 5.6
``yaml
sudo update-alternatives --set php /usr/bin/php5.6
sudo update-alternatives --set phar /usr/bin/phar5.6
sudo update-alternatives --set phar.phar /usr/bin/phar.phar5.6
sudo update-alternatives --set phpize /usr/bin/phpize5.6
sudo update-alternatives --set php-config /usr/bin/php-config5.6
```
