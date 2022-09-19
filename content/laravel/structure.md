---
title: "Structure"
date: 2022-09-14T13:50:15+02:00
draft: false
tags: ['laravel']
---

[Go Back]({{< ref "/laravel/summary.md" >}} "getdafucoutahere")

# Contents
* <a href="#overview">General File Structure Overview</a>
* <a href="#note">Note when you're "migrating" from another framework to this new shithole :)</a>
* <a href="#shortcuts">Shortcuts</a>

<div id="overview"></div>

# General File Structure Overview
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
* **Middleware** - the security guard / validations boi; can be used in routing;found in Http/Middleware
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

<div id="note"></div>

## Something to note when you're *"migrating"* from another framework to this new shithole :)
* Columns in a table are declared in the migrations
* Tables/Entities are migrated when you EXPLICITLY type in `make:migration create_NAME-OF-YOUR-MODELs_table`, yes, plural
  * OR when you're just creating a new model `make:model NameOfModel -m` // I think -m means migration
  * TRY this out as well `make:model -mrc EntitysName` <- the model will become singular but plural when migrated
    * it *should* make a controller with resource functions in it + a model
    * <a href="https://youtu.be/2bz5eleBj98?t=3600" target="_blank">[video link]</a>
