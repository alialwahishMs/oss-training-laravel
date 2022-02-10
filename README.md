# Creating Laravel application

## Requirements

- [PHP 7.x](https://windows.php.net/download/)
- [Composer](https://getcomposer.org/download/)

## Installing Lavavel via Composer

1. Open a new terminal to run the following command: Change *example-app* to the name of your application.

```cmd
composer create-project laravel/laravel example-app
```

2. CD into your newly created project and type **`code .`** to open the current directory in Visual Studio Code.

If you are running a fresh PHP installation, you can use this example [php.ini](https://chmaldstorage.blob.core.windows.net/phpwpbootcamp/php.ini) files for your PHP installation.

## Setting up Laravel

Before you are able to continue further, you will need to ensure your `.env` file has a `APP_KEY` defined. To generate a new `APP_KEY` run the following command:

```cmd
php artisan key:generate
```

To start and run Laravel,  using the following command:

```cmd
php artisan serve
```

Navigate to `http://localhost:8080` to access your new Laravel application.

To stop running your application locally, press `CTRL+C`.

## Creating a new Controller

Controllers can be used to display data for a REST API or even to show an application page.

Create a new controller using the following command:

```cmd
php artisan make:controller HelloWorldController
```

This will create a new file `app\Http\Controllers\HelloWorldController.php`

Navigate to the new controller file and add a new function inside the defined class.

```php
public function index()
{
    return "Hello World";
}
```

## Creating a new Route

In order to access this new function, you will need to define a route.

Open the `routes\web.php` file and add the new controller with the route `/hello`.

Within the `Route:get()` function we are setting the `/hello` endpoint to point to `HelloWorldController:class` and the `index` function we defined.

```php
<?php

use Illuminate\Support\Facades\Route;
use App\Http\Controllers\HelloWorldController;

/*
|--------------------------------------------------------------------------
| Web Routes
|--------------------------------------------------------------------------
|
| Here is where you can register web routes for your application. These
| routes are loaded by the RouteServiceProvider within a group which
| contains the "web" middleware group. Now create something great!
|
*/

Route::get('/', function () {
    return view('welcome');
});

Route::get('/hello', [HelloWorldController::class, 'index']);
```

Once added, run your application using `php artisan serve`.

Navigate to your new endpoint: [http://localhost:8000/hello](http://localhost:8000/hello)

## Expand your knowledge

Create two additional endpoints using the resources below to expand your knowledge:

[Laravel - Controller](https://laravel.com/docs/8.x/controllers)

[Laravel - Responses](https://laravel.com/docs/8.x/responses)