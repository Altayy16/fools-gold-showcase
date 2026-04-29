FROM php:8.3-fpm

# Install necessary system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# Clear cache to keep the image small
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install standard Laravel PHP extensions
RUN docker-php-ext-install pdo_mysql mbstring pcntl bcmath gd

# Install Redis extension for caching and Reverb
RUN pecl install redis && docker-php-ext-enable redis

# Set working directory
WORKDIR /var/www/html