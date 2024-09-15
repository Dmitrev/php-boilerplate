FROM php:8.3-fpm

ARG USER_ID
ARG GROUP_ID

RUN userdel -f www-data &&\
    if getent group www-data; then groupdel www-data; fi &&\
    groupadd  -g ${GROUP_ID} www-data &&\
    useradd -l -u ${USER_ID} -d /home/www-data -g www-data www-data &&\
    # install -d -m 0755 -o www-data -g www-data /home/www-data &&\
    chown --changes --silent --no-dereference --recursive \
        --from=33:33 ${USER_ID}:${GROUP_ID} \
        /home/www-data\
        /usr/local/etc/php \
        /usr/local/etc/php-fpm.d

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    locales \
    libzip-dev \
    zip \
    vim \
    unzip \
    git \
    curl

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install extensions
RUN docker-php-ext-install bcmath pdo_mysql zip

# Install composer
RUN curl --silent --show-error https://getcomposer.org/installer | php -- \
    --install-dir=/usr/local/bin \
    --filename=composer


# Any binaries installed through composer become available in the $PATH
ENV PATH "$PATH:/var/data/www/vendor/bin"

USER www-data

CMD ["php-fpm"]
