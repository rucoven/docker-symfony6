#FROM php:8.0.18-fpm-alpine3.15
FROM php:8.0-rc-fpm-alpine

RUN apk --no-cache update && apk --no-cache add bash git 

RUN docker-php-ext-install pdo_mysql \
&& docker-php-source delete 

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
&& php composer-setup.php \
&& php -r "unlink('composer-setup.php');" \
&& mv composer.phar /usr/local/bin/composer \
&& wget https://github.com/symfony-cli/symfony-cli/releases/download/v5.4.8/symfony-cli_5.4.8_x86_64.apk \
&& apk add --allow-untrusted symfony-cli_5.4.8_x86_64.apk \
&& rm symfony-cli_5.4.8_x86_64.apk 

WORKDIR /var/www

CMD composer install ;  php-fpm

EXPOSE 9000



# && wget https://get.symfony.com/cli/installer -O - | bash \
# && mv /root/.symfony/bin/symfony /usr/local/bin/symfony

