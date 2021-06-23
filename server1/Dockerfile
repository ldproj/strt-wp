FROM wordpress:php8.0-apache
LABEL Name=ssl-wordpress:latest Version=0.0.2

# Enabling the SSL module
RUN a2enmod ssl && a2enmod rewrite

# Copy the SSL certs to the image
RUN mkdir -p /etc/apache2/certs

COPY ../ssl/*.pem /etc/apache2/ssl/

# Copy config to the image
COPY ../apache/*.conf /etc/apache2/sites-available/

# make available outside the container
EXPOSE 80
EXPOSE 443
