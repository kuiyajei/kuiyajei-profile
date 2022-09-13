---
title: "Cheat Sheet / Summary"
date: 2022-09-12T07:49:34+02:00
draft: false
tags: ['laravel']
---

[Back to Home]({{< ref "home.md" >}} "Back to Home")

![floppa](/laravel/images/floppa_poly.png)  <br/>
*my notes have references to .NET Core so this might not actually be helpful*

Based **TraversyMedia's Laravel Crash Course** | Uploaded: Apr. 26, 2022: [[link]](https://youtu.be/MYyJ4PuL4pY)

## Installation for Windows
---
Software you need...
- something to run Linux commands, so install GitBash (the documentation tells you to get Docker but don't mind that)
- Composer
- to run the following in a terminal (assuming you're going to use Laravel for quite a while and it's not just a one time thing):
  ``composer global require laravel/installer``.
  Then in the directory where you want to work on, open a terminal there and ``laravel new name-of-your-app``. If it's the latter, then do this instead of the above ``composer create-project laravel/laravel name-of-your-app``.

## File Structure
---
* **Views** - resources/views/[name].blade.php
* **Routes** - Where we'll load in Views and Controllers *(you know how in .NET Core's MVC Controllers have IActionResult? This is pretty similar to that, except the return part's separated to here.)*
* **Models** - app/Models
  * (Manual) - go to Models folder and create a file there. You need to add other stuff like namespace and A LOT of other required stuff, but like, w h y . . . ? When you have...
  * (Fancy/Best) - ``php artisan make:model name-of-model``
* **Database Setup**
  1. ) config/database.php ``'default' => env('DB_CONNECTION', 'mysql'),`` mysql is replacable if need be
  2. ) you can configure other stuff in ".env", and [click here to setup your MySQL](https://youtu.be/MYyJ4PuL4pY?t=2754) unless you have...
  3. ) XAMPP, in which case all you need to do is run APACHE and MySQL. MySQL -> click Admin on the UI 
  4. ) Make sure to edit DB_DATABASE in ".env" if you have a different name for the database you're going to use
* **Migrations** - database/migrations 
  * ***REMINDER:*** The tutorial at first shows you to migrate and seed, and not just migrate the model.
  * ***also:*** From the way it looks, it migrates EVERYTHING inside the migrations folder - at least initially (this is just an assumption)
* **Seeding** - database/seeders
* **Themes** - setup's long, click [(here)]({{< ref "laravel/themes.md" >}} "(link)") when you're ready | <a href="https://youtu.be/MYyJ4PuL4pY?t=4318" target="_blank">[video link]</a>

## Laravel Programming Concepts
---
* **Wild Cards** - Similar to asp-route-id
* **Route Constraints** - ``->where('param', 'regex stuff here')``, useful for validations
* **Debugging - dd** - Shows you what's passed in
* **Debugging - ddd** - Detailed debug info
* **Directives @** - oh hey, it's like the front-end of .NET Core except you have to put them at the start and end of something like a foreach
  * *@php* can sometimes be useful if you can't perform stuff on the controller or route
* **Request & Query** - Useful for search functions
* **Layout & Sections** - Useful for headers and footers. This one's kinda confusing <a href="https://youtu.be/MYyJ4PuL4pY?t=4099" target="_blank">so here</a>
  * In the layout:
    * ``@yield('matching-content-name')`` this is where you want the view to be displayed at when the view extends the layout
  * In the View extending the layout: 
    * ``@extends('layout-name')`` put this on the very top
    * ``@section('content-name')`` and ``@endsection`` then wrap that around the content you want as a section
  * **Components** - useful if you want to pass in stuff...? <a href="https://www.educba.com/laravel-components/" target="_blank">[link]</a>

## Relevant CLI commands for Laravel
---
Write ``php artisan`` space...
* ``serve`` - run the site locally
* ``make:migration name-of-migration`` - add migration
* `` migrate`` - migrates the latest
* `` db:seed`` - seed
  * ``migrate:refresh`` - can be useful if you suddenly edit or remove data in the seed
  * *(don't put a space here)* ``:migrate:refresh`` --seed refresh && seed 
* ``make:model name-of-model`` - make a model
* 

## Optional but cool (stuff I'm not familiar with even outside of the regular MVC sh*t)
---
* **Faker** - I really am not familiar with this <a href="https://youtu.be/MYyJ4PuL4pY?t=3791" target="_blank">so...</a>
  * **php artisan make:factory name-of-factory**
  * **Example:** ``'title' => $this -> faker -> sentence(),``
    * sentence can be replaced by other formats found <a href="https://github.com/fzaninotto/Faker#table-of-contents" target="_blank">here</a>


## Useful extensions
---
* **PHP Namespace Resolver** - Really useful for importing libraries and classes that act like VS' auto-fill feature
* **PHP Intelephense** - Good for PHP dev in general