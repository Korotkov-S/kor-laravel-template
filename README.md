# laravel-template
Is laravel backend template

<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 2000 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[WebReinvent](https://webreinvent.com/)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Jump24](https://jump24.co.uk)**
- **[Redberry](https://redberry.international/laravel/)**
- **[Active Logic](https://activelogic.com)**
- **[byte5](https://byte5.de)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## Setting

Install the [Composer](https://getcomposer.org/download/)

Install the [MySql](https://www.mysql.com)

Clone the repository

```shell
git clone git@github.com:Korotkov-S/korotkov-landing-backend.git
```

Go to directory

Install dependencies

```shell
composer global require laravel/installer
```

Install the composer 

```shell
composer install
```

Add .env file with data

Create a database in MySql

## Creating tables

```shell
php artisan make:migration create_[name_table]_table
```
Table name must be in plural

### Adding tables to the database

```shell
php artisan migrate
```

## Creating model

```shell
php artisan make:model NameModel
```

## Creating controller

```shell
php artisan make:controller NameControllerController
```

## Creating seeder

```shell
php artisan make:seeder NameSeederSeeder
```

### Running Seeders

```shell
php artisan db:seed
```

For specific seeder class to run

```shell
php artisan db:seed --class=NameSeeder
```

## Creating Form Requests

```shell
php artisan make:request NameRequestRequest
```

In function **authorize()** set return value to true

## Admin bar start

In the browser bar, specify the _admin_ path
```shell
http://127.0.0.1:8000/admin
```

### Admin addition

Administrator an existing user
```shell
php artisan voyager:admin your@email.com
```

If you wish to create a new admin user you can pass the --create
```shell
php artisan voyager:admin your@email.com --create
```

## Swagger launch

For example (in a controller)
```shell
/**
 * @OA\Post(
 *     path="/api/name_animals",
 *     summary="Пример",
 *     tags={"Country"},
 * 
 *     @OA\RequestBody(
 *         @OA\JsonContent(
 *             allOf={
 *                 @OA\Schema(
 *                     @OA\Property(property="name", type="string", example="Тукан"),
 *                 ),
 *             },
 *         ),
 *     ),
 * 
 *     @OA\Response(
 *         response=200,
 *         description="ОК",
 *         @OA\JsonContent(
 *             @OA\Property(property="data", type="string", example="Название успешно добавлено!"),
 *         ),
 *     ),
 *     @OA\Response(
 *         response=422,
 *         description="Unprocessable Content",
 *         @OA\JsonContent(
 *             @OA\Property(property="message", type="string", example="Заполните поле название!"),
 *             @OA\Property(property="errors", type="object",
 *                 @OA\Property(property="name", type="array",
 *                     @OA\Items(type="string", example="Заполните поле название!"),
 *                 ),
 *             ),
 *         ),
 *     ),
 * ),
 */
```

To generate swagger you need
```shell
php artisan 5-swagger:generate
```

## Work with files

For example, if you are working with s3 repository, you need in .env file 
```shell
AWS_URL=https://[bucket].s3.timeweb.com
AWS_ENDPOINT=http://s3.timeweb.com
```

## Laravel Pint Launch

```shell
./vendor/bin/pint
```

## Psalm Launch

```shell
./vendor/bin/psalm 
```

## The launch of the application

Run the application
```shell
php artisan serve
```

Run the application with the necessary variables
```shell
php artisan serve --env={name}
```

The application is available at http://127.0.0.1:8000