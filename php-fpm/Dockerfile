FROM php:7.3-fpm-alpine
WORKDIR '/app'
COPY installer .
RUN php -- --install-dir=/usr/bin/ --filename=composer \
    composer install --no-dev --no-interaction -o
COPY symfony.ini /etc/php7.3/conf.d/
COPY symfony.ini /etc/php7.3/cli/conf.d/
COPY symfony.pool.conf /etc/php7.3/php-fpm.d/

CMD ["php-fpm", "-F"]
WORKDIR /var/www/symfony

EXPOSE 9001