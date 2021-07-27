<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>

# Inventaris Lab

Langkah-langkah intalasi :

1. Buat database
2. Copy file .env.example menjadi .env lalu sesuaikan user, password, dan database
3. Kemudian eksekusi perintah berikut di terminal/command prompt
    > `$ composer update` > `$ npm install` > `$ npm run dev` > `$ php artisan migrate` > `$ php artisan key:generate` > `$ php artisan jwt:secret`

## API Specification

This application adheres to the api specifications set by the [Thinkster](https://github.com/gothinkster) team. This helps mix and match any backend with any other frontend without conflicts.

> [Full API Spec](https://github.com/gothinkster/realworld/tree/master/api)

More information regarding the project can be found here https://github.com/gothinkster/realworld

---

## Dependencies

-   [jwt-auth](https://github.com/tymondesigns/jwt-auth) - For authentication using JSON Web Tokens
-   [laravel-cors](https://github.com/barryvdh/laravel-cors) - For handling Cross-Origin Resource Sharing (CORS)

## Folders

-   `app` - Contains all the Eloquent models
-   `app/Http/Controllers/Api` - Contains all the api controllers
-   `app/Http/Middleware` - Contains the JWT auth middleware
-   `app/Http/Requests/Api` - Contains all the api form requests
-   `config` - Contains all the application configuration files
-   `database/factories` - Contains the model factory for all the models
-   `database/migrations` - Contains all the database migrations
-   `database/seeds` - Contains the database seeder
-   `routes` - Contains all the api routes defined in api.php file
-   `tests` - Contains all the application tests
-   `tests/Feature/Api` - Contains all the api tests

## Environment variables

-   `.env` - Environment variables can be set in this file

**_Note_** : You can quickly set the database information and other variables in this file and have the application fully working.

---

# Testing API

Run the laravel development server

    php artisan serve

The api can now be accessed at

    http://localhost:8000/api

Request headers

| **Required** | **Key**          | **Value**        |
| ------------ | ---------------- | ---------------- |
| Yes          | Content-Type     | application/json |
| Yes          | X-Requested-With | XMLHttpRequest   |
| Optional     | Authorization    | Token {JWT}      |

Refer the [api specification](#api-specification) for more info.

---

# Authentication

This applications uses JSON Web Token (JWT) to handle authentication. The token is passed with each request using the `Authorization` header with `Token` scheme. The JWT authentication middleware handles the validation and authentication of the token. Please check the following sources to learn more about JWT.

-   https://jwt.io/introduction/
-   https://self-issued.info/docs/draft-ietf-oauth-json-web-token.html

---

# Cross-Origin Resource Sharing (CORS)

This applications has CORS enabled by default on all API endpoints. The default configuration allows requests from `http://localhost:3000` and `http://localhost:4200` to help speed up your frontend testing. The CORS allowed origins can be changed by setting them in the config file. Please check the following sources to learn more about CORS.

-   https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS
-   https://en.wikipedia.org/wiki/Cross-origin_resource_sharing
-   https://www.w3.org/TR/cors
