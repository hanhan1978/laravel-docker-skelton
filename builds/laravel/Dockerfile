FROM php:7.1-apache

RUN a2enmod rewrite

RUN rm -rf /var/www/html \
  && ln -s /var/www/laravel/public /var/www/html

EXPOSE 80
