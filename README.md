# Nginx Php Docker

This is a docker build file for Nginx + Php Docker.

Environments<br>
OVERRIDE_URL - An url to a zip which contain files that you want to override (php.ini, www.conf or nginx.conf) 

/etc/php/x.x/fpm/php.ini<br>
/etc/php/x.x/fpm/conf.d/www.conf<br>
/etc/nginx/nginx.conf<br>

SOURCE_URL - An url to download your source code and copy to /var/www/html/
/var/www/html is the root folder for nginx

You can pull the docker from
https://hub.docker.com/r/brontocloud/nginx-php
