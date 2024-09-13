FROM php:8.3-fpm

ARG USER_NAME
RUN useradd $USER_NAME

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


USER $USER_NAME
# Any binaries installed through composer become available in the $PATH
ENV PATH "$PATH:/var/data/www/vendor/bin"

CMD ["php-fpm"]
