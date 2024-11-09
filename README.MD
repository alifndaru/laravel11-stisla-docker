# Laravel 11 with Stisla Template

Welcome to the repository for Laravel 11 integrated with Stisla Bootstrap 5 template!

# point penting
# Artisan commands
docker-compose exec app php artisan tinker
docker-compose exec app php artisan make:controller UserController

# NPM commands
docker-compose exec node npm run dev
docker-compose exec node npm run build
## Overview

This repository contains a Laravel 11 template that comes pre-configured with authentication from Breeze and utilizes the Stisla Bootstrap 5 template for the UI.

## Prerequisites

- PHP >= 8.2
- Composer
- Node.js & npm
- Docker & Docker Compose (for containerized environment)

## Installation Options

You can run this project either locally or using Docker. Choose the method that best suits your needs.

### Local Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd laravel11-stisla
```

2. Install dependencies:
```bash
composer install
npm install
```

3. Set up environment:
```bash
cp .env.example .env
php artisan key:generate
```

4. Run migrations:
```bash
php artisan migrate
```

5. Build assets:
```bash
npm run dev
```

6. Start local server:
```bash
php artisan serve
```

### Docker Installation

1. Clone and enter the repository:
```bash
git clone <repository-url>
cd laravel11-stisla
```

2. Copy environment file:
```bash
cp .env.example .env
```

3. Start Docker containers:
```bash
docker compose up -d --build
```

4. Set up the application:
```bash
# Install PHP dependencies
docker compose exec app composer install

# Install Node dependencies and build assets
docker compose exec app npm install
docker compose exec app npm run dev

# Generate application key
docker compose exec app php artisan key:generate

# Run migrations
docker compose exec app php artisan migrate
```

## Docker Commands Reference

### Basic Commands
```bash
# Start containers
docker compose up -d

# Stop containers
docker compose down

# View container status
docker compose ps

# View logs
docker compose logs -f
```

### Development Commands
```bash
# Access container shell
docker compose exec app sh

# Run artisan commands
docker compose exec app php artisan <command>

# Install new packages
docker compose exec app composer require <package-name>

# Generate Laravel files
docker compose exec app php artisan make:model ModelName
docker compose exec app php artisan make:controller ControllerName
```

### Database Commands
```bash
# Fresh migration
docker compose exec app php artisan migrate:fresh

# Run seeders
docker compose exec app php artisan db:seed

# Remove database volume
docker compose down -v
```

### Cache Commands
```bash
# Clear various caches
docker compose exec app php artisan cache:clear
docker compose exec app php artisan config:clear
docker compose exec app php artisan view:clear
```

## Accessing the Application

- Web Application: `http://localhost`
- Database (PostgreSQL):
  - Host: `localhost`
  - Port: `5432`
  - Credentials: As configured in your `.env` file

## Troubleshooting

### Permission Issues
```bash
docker compose exec app chown -R www-data:www-data storage bootstrap/cache
```

### Container Issues
- Check container logs: `docker compose logs -f`
- Ensure ports 80 and 5432 are available
- Rebuild containers if Dockerfile changes: `docker compose up -d --build`

## Development Tips

1. Always check logs for errors
2. Regularly backup your database
3. Keep your containers updated
4. Use version control for your changes

## Contributing

Please read our contributing guidelines before submitting pull requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
