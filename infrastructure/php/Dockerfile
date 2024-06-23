FROM php:8.1-fpm-alpine AS base

#install php extension
RUN docker-php-ext-install pdo pdo_mysql

#allow as superuser in variable
ENV COMPOSER_ALLOW_SUPERUSER=1


##get composer as img into location in img
COPY --from=composer:2.4 /usr/bin/composer /usr/bin/composer
##copy files before install into same location, uses docker cache -> install runs only if changed in files
COPY ./composer.* ./
##install
RUN composer install --prefer-dist --no-dev --no-scripts --no-progress --no-interaction --ignore-platform-reqs

#copy app files to work dir => var/www/html
COPY ./app .

#run autoload
RUN composer dump-autoload --optimize