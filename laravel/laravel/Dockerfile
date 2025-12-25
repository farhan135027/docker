FROM php

RUN apt-get update
RUN apt-get install -y --no-install-recommends \
        git \
        nodejs \
        npm \
        libzip-dev

RUN docker-php-ext-install \
        pdo_mysql \
        zip

COPY --from=composer /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/laravel
EXPOSE 8000
ENTRYPOINT ["sh", "entrypoint.sh"]