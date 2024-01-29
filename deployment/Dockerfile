FROM php:8.1-apache
RUN docker-php-ext-install pdo pdo_mysql 
WORKDIR /var/www/html

# Copy essential files
COPY . .

# Install Composer dependencies
RUN composer install

# Generate application key
RUN php artisan key:generate --force

# Create storage and cache directories
RUN mkdir -p storage/framework && chmod -R 777 storage

# Set working directory for Apache
RUN echo "Npontu laravel" >> /etc/apache2/sites-enabled/000-default.conf && echo "DocumentRoot /var/www/html/public" >> /etc/apache2/sites-enabled/000-default.conf

EXPOSE 80

# Redirect Apache logs to stdout/stderr
RUN ln -sf /dev/stdout /var/log/apache2/access.log \
    && ln -sf /dev/stderr /var/log/apache2/error.log



# Health check
HEALTHCHECK --interval=30s --timeout=3s \
  CMD curl -f http://localhost/ || exit 1


# Run Apache process
CMD ["apache2", "foreground"]










