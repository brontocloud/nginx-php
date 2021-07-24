FROM debian:buster-slim
MAINTAINER https://bronto.cloud

RUN apt-get update && apt-get -y install vim unzip wget supervisor php7.3-fpm php7.3-mbstring php7.3-mysql php7.3-redis php7.3-xml php7.3-json php7.3-zip php7.3-gd php7.3-imagick php7.3-tokenizer php7.3-common php7.3-soap php7.3-curl nginx

RUN mkdir -p /var/log/supervisor

COPY supervisord/supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY nginx/default /etc/nginx/sites-available/default
COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY php/php.ini /etc/php/7.3/fpm/php.ini
COPY bronto/bronto /bin/bronto
COPY bronto/bronto_init /bin/bronto_init

RUN chmod +x /bin/bronto
RUN chmod +x /bin/bronto_init

RUN rm -rf /var/www/html/*
CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
