---
title: "Structure"
date: 2022-09-14T13:50:15+02:00
draft: false
tags: ['laravel']
---

[Back to Home]({{< ref "/laravel/summary.md" >}} "Go Back.")

## File Structure
---
* **Views** - resources/views/[name].blade.php
* **Routes** - Where we'll load in Views and Controllers *(you know how in .NET Core's MVC Controllers have IActionResult? This is pretty similar to that, except the return part's separated to here.)*
* **Models** - app/Models
  * (Manual) - go to Models folder and create a file there. You need to add other stuff like namespace and A LOT of other required stuff, but like, w h y . . . ? When you have...
  * (Fancy/Best) - ``php artisan make:model name-of-model``
* **Controller** - ``php artisan make:controller name-of-subfolder/nameofController``. You'll find the controller inside *app > Http > Controllers*. 
  * To use this go to `routes > web.php` and `use App\Http\Controllers`
  * OR if you have the cool extensions it'll import the appropriate files for you as you type the code
  * `Route::get('/name-of-view', [NameOfController::class, 'MethodName']);` for singular routes
  * `Route::controller(testController::class)->group(function () { });` and inside the curly braces `Route::get('/name-of-view','MethodName')->('name-for-long-URLs.page');` to group a controller with multiple methods
* Middleware - the security guard / validations boi; can be used in routing
* **Database Setup**
  1. ) config/database.php ``'default' => env('DB_CONNECTION', 'mysql'),`` mysql is replacable if need be
     1. ) you can configure other stuff in ".env", and [click here to setup your MySQL](https://youtu.be/MYyJ4PuL4pY?t=2754) unless you have...
  2. ) XAMPP, in which case all you need to do is run APACHE and MySQL. MySQL -> click Admin on the UI 
  3. ) Make sure to edit DB_DATABASE in ".env" if you have a different name for the database you're going to use
* **Migrations** - database/migrations 
  * ***REMINDER:*** The tutorial at first shows you to migrate and seed, and not just migrate the model.
  * ***also:*** From the way it looks, it migrates EVERYTHING inside the migrations folder - at least initially (this is just an assumption)
* **Seeding** - database/seeders
* **Themes** - setup's long, click [(here)]({{< ref "laravel/themes.md" >}} "(link)") when you're ready | <a href="https://youtu.be/MYyJ4PuL4pY?t=4318" target="_blank">[video link]</a>
