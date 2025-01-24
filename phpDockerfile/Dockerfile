FROM php:8.2-alpine3.20

CMD ["bash"]

RUN apk update -q && \
    apk add -q --no-cache \
    libpq-dev \
    icu-dev \
    icu-libs \
    php-cli \
    php-phar \
    php-openssl \
    php-mbstring \
    php-tokenizer \
    php-json \
    php-iconv \
    php-ctype \
    php-curl \
    php-dom \
    php-xml \
    curl \
    wget \
    git \
    && docker-php-ext-install pdo_pgsql pgsql \
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl \
    && docker-php-ext-enable intl

RUN curl -sS https://getcomposer.org/installer -o ~/composer-setup.php

RUN php ~/composer-setup.php --install-dir=/usr/local/bin --filename=composer

RUN rm ~/composer-setup.php

RUN apk del icu-dev
