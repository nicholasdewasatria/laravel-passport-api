
# Laravel Passport API

This is a simple Laravel 11 RESTful API project using Laravel Passport for authentication. It includes basic CRUD operations for a `Product` resource.

## Features

- Laravel Passport authentication
- Register and login API
- CRUD API for products (Create, Read, Update, Delete)

## Requirements

- PHP >= 8.2
- Composer
- Laravel 11
- MySQL or other database
- Git

## Installation

1. **Clone the repository**

```bash
git clone https://github.com/nicholasdewasatria/laravel-passport-api.git
cd laravel-passport-api
```

2. **Install dependencies**

```bash
composer install
```

3. **Set environment file**

```bash
cp .env.example .env
```

Configure your `.env` file with your database settings.

4. **Generate application key**

```bash
php artisan key:generate
```

5. **Run migrations**

```bash
php artisan migrate
```

6. **Install Passport**

```bash
php artisan passport:install
```

7. **Run the server**

```bash
php artisan serve
```

## API Endpoints

### Authentication

- `POST /api/register`  
  Register a new user. Example:
  ```json
  {
    "name": "Messi",
    "email": "messi@example.com",
    "password": "password",
    "password_confirmation": "password"
  }
  ```

- `POST /api/login`  
  Login and get access token. Example:
  ```json
  {
    "email": "messi@example.com",
    "password": "password"
  }
  ```

### Products (Authenticated)

Add `Authorization: Bearer {token}` to the headers.

- `GET /api/products`  
  List all products.

- `GET /api/products/{id}`  
  Get product details by ID.

- `POST /api/products`  
  Create a product. Example:
  ```json
  {
    "name": "Football",
    "detail": "Adidas Pro Match Ball",
    "price": 99.99
  }
  ```

- `PUT /api/products/{id}`  
  Update a product. You can send only fields you want to change. Example:
  ```json
  {
    "name": "Football Updated"
  }
  ```

- `DELETE /api/products/{id}`  
  Delete a product.

## License

This project is open source and available under the [MIT License](LICENSE).
