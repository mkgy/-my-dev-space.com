# Laravel Social Media Website
This project is credited to the following YouTube Tutorial:
[YouTube Tutorial](https://www.youtube.com/watch?v=4iiEyOKhvao&list=PLLQuc_7jk__Wa8IoZ2s0J-ql_MIisndtZ).
and was cloned by me with the sole purpose to educate myself about deploying a Laravel app built with Inertia Vue.js on Hostinger.

## 
*
*
## Demo
The application is deployed on the following domain [laravel-space.com](https://my-dev-space.com/)

## Installation with docker

#### 1. Clone the project
```bash
git clone https://github.com/mkgy/my-dev-space.com.git
```

#### 2. Run `composer install`
Navigate into project folder using terminal and run

```bash
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php83-composer:latest \
    composer install --ignore-platform-reqs
```

#### 3. Copy `.env.example` into `.env`

```bash
cp .env.example .env
```

#### 4. Start the project in detached mode

```bash
./vendor/bin/sail up -d
```
From now on whenever you want to run artisan command you should do this from the container. <br>
Access to the docker container
```bash
./vendor/bin/sail bash
```

#### 5. Set encryption key

```bash
php artisan key:generate --ansi
```

#### 6. Run migrations

```bash
php artisan migrate
```

