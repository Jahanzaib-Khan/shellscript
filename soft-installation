#!/bin/bash

# Update package lists
sudo apt-get update

# Install Apache
sudo apt-get install -y apache2

# Install PHP and required modules
sudo apt-get install -y php libapache2-mod-php

# Install Git
sudo apt-get install -y git

# Configure Apache to handle PHP files
sudo sed -i 's/index.html/index.php/g' /etc/apache2/mods-enabled/dir.conf
sudo systemctl restart apache2

# Create a sample PHP file to test
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php

# Set permissions to the web directory (adjust as needed)
sudo chown -R www-data:www-data /var/www/html/
sudo chmod -R 755 /var/www/html/

# Enable Apache to start on boot
sudo systemctl enable apache2

# Output information
echo "Apache, PHP, and Git have been installed and configured."
echo "You can access the PHP info page at http://your-server-ip/info.php"
