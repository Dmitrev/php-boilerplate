FROM php:8.1-fpm

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

CMD ["php-fpm"]
