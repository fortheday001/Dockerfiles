FROM fortheday001/php

MAINTAINER "fortheday fortheday@126.com"

WORKDIR /var/www/html

RUN git clone https://github.com/fortheday001/api-shop1.git .

RUN chown -R www-data:www-data storage

VOLUME ["/var/www/html"]

RUN composer install