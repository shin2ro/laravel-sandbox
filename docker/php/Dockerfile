FROM php:7.4-cli

RUN apt update \
    && apt install -y libxml2-dev libonig-dev \
    && docker-php-ext-install bcmath json mbstring xml pdo_mysql mysqli \
    && apt clean \
    && rm -rf /var/lib/apt/lists/*

COPY php.ini $PHP_INI_DIR/php.ini
