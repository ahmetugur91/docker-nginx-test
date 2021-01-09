FROM php:7.4-fpm

RUN apt-get update && apt-get install -y libmcrypt-dev

RUN docker-php-ext-install pdo
RUN pecl install mcrypt
RUN docker-php-ext-enable mcrypt

#id $user komutunu calıstır ordan userin id yi al 0 la yer değiştir.
#RUN groupadd -g 0 www
#RUN useradd -u 0 -ms /bin/bash -g www www

WORKDIR /var/www
COPY --chown=www-data:www-data ./site1/socket-redis /var/www
USER www-data

EXPOSE 9000
CMD ["php-fpm"]