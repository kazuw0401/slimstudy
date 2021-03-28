FROM php:7.4-fpm
COPY --from=composer /usr/bin/composer /usr/bin/composer
RUN apt-get update && \
    apt-get -y install unzip libzip-dev libicu-dev libonig-dev
RUN docker-php-ext-install -j$(nproc) intl mbstring pdo pdo_mysql \
    && pecl install xdebug && \
    docker-php-ext-enable xdebug
