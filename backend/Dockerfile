FROM php:7.2-apache
ENV APACHE_DOCUMENT_ROOT /var/www/html/public

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

RUN docker-php-ext-install mysqli pdo_mysql

RUN a2enmod rewrite
RUN service apache2 restart

# CMD ["/usr/sbin/apache2", "-D",  "FOREGROUND"]

WORKDIR /var/www/html/