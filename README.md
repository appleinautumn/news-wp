# News WordPress Tutorial

This project is a WordPress tutorial website built with custom theme and functionality.

## Prerequisites

- PHP 7.4 or higher
- MySQL 5.7 or higher
- Node.js and npm
- WP-CLI

## Installation

### 1. Install WP-CLI

If you don't have WP-CLI installed, run:

```bash
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
chmod +x wp-cli.phar
sudo mv wp-cli.phar /usr/local/bin/wp
```

Verify installation:
```bash
wp --info
```

### 2. Install WordPress

```bash
# Create database (if needed)
mysql -u root -p -e "CREATE DATABASE news_wp;"
mysql -u root -p -e "GRANT ALL PRIVILEGES ON news_wp.* TO 'your_username'@'localhost';"

# Download WordPress core
wp core download

# Create wp-config.php
wp config create --dbname=news_wp --dbuser=your_username --dbpass=your_password

# Install WordPress
wp core install --url=http://localhost/news-wp --title="News WordPress" --admin_user=admin --admin_password=password --admin_email=your-email@example.com
```

### 3. Import Database (Optional)

```bash
# Extract database
tar -xzf newswp-db-2025-02-10.sql.tar.gz

# Import
wp db import newswp-db-2025-02-10.sql
```

### 4. Theme Development

```bash
cd wp-content/themes/fictional-university-theme
npm install
npm run dev
```

## Features

- Custom post types: Events, Programs, Professors, Campuses
- Advanced Custom Fields integration
- Interactive campus map with Google Maps API
- Live search functionality

## Development

- Run `npm run dev` to start development server
- Run `npm run build` for production build