# Clean Laravel 12 Setup

A ready-to-use Laravel 12 project template for developers with slow internet connections. Instead of running `composer create-project laravel/laravel` which downloads large dependencies, simply clone this repository and set it up locally.

## Prerequisites

Before you begin, make sure you have the following installed:

- [PHP 8.2 or higher](https://www.php.net/downloads.php)
- [Composer](https://getcomposer.org/)
- [Node.js & npm](https://nodejs.org/)
- [Git](https://git-scm.com/)

## Getting Started

Clone this repository:

```bash
git clone https://github.com/wyattmatt/clean-laravel-12-setup.git
cd clean-laravel-12-setup
```

## Quick Setup (Recommended)

Run the automated setup script that handles everything for you:

```bash
composer setup
```

This command will:
- Install PHP dependencies
- Copy `.env.example` to `.env`
- Generate application key
- Create SQLite database and run migrations
- Install JavaScript dependencies
- Build frontend assets

Then start the development server:

```bash
php artisan serve
```

Your application will be available at `http://localhost:8000`

## Manual Setup

If you prefer to set up step by step:

1. **Install Composer dependencies**
   ```bash
   composer install
   ```

2. **Copy environment file**
   ```bash
   cp .env.example .env
   ```

3. **Generate application key**
   ```bash
   php artisan key:generate
   ```

4. **Create database and run migrations**
   ```bash
   type nul > database/database.sqlite                        # CMD
   New-Item -Path database/database.sqlite -ItemType File     # PowerShell
   touch database/database.sqlite                             # Linux/Mac
   php artisan migrate
   ```

5. **Install JavaScript dependencies** (optional, needed for frontend assets)
   ```bash
   npm install
   npm run build
   ```

6. **Start the development server**
   ```bash
   php artisan serve
   ```

## Development Mode

For active development with hot module replacement, use the full development environment:

```bash
composer dev
```

This command runs:
- Laravel development server
- Queue worker
- Log viewer (Pail)
- Vite dev server with hot reload

All services run concurrently and will stop together when you press Ctrl+C.

Alternatively, run them separately in different terminal windows:

```bash
# Terminal 1: Laravel server
php artisan serve

# Terminal 2: Vite dev server (for frontend)
npm run dev
```

## Testing

Run the test suite:

```bash
composer test
```
