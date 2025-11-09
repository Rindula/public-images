FROM %BASEIMAGE%

LABEL BASEIMAGE %BASEIMAGE%

RUN apt-get update && apt-get install -y build-essential libpng-dev libjpeg62-turbo-dev libfreetype6-dev locales zip jpegoptim optipng pngquant gifsicle vim unzip git curl libzip-dev libonig-dev mysql-common libldap2-dev libicu-dev
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-configure intl
RUN docker-php-ext-install mysqli pdo_mysql opcache gd exif intl zip fileinfo
RUN docker-php-ext-enable mysqli pdo_mysql opcache gd exif intl zip fileinfo

RUN a2enmod rewrite
RUN a2enmod headers
