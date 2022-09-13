---
title: "Basics"
date: 2022-09-12T07:49:34+02:00
draft: false
tags: ['laravel']
---

[Back to Home]({{< ref "home.md" >}} "Back to Home")

![floppa](/laravel/images/floppa_poly.png)  <br/><br/>
hi

## Installation for Windows
---
Software you need...
- something to run Linux commands, so install GitBash (the documentation tells you to get Docker but don't mind that)
- Composer
- to run the following in a terminal (assuming you're going to use Laravel for quite a while and it's not just a one time thing):
  "composer global require laravel/installer".
  Then in the directory where you want to work on, open a terminal there and "laravel new name-of-your-app". If it's the latter, then do this instead of the above "composer create-project laravel/laravel name-of-your-app".

## File Structure
---
* **Views** - resources/views/[name].blade.php
* **Routes** - Where we'll load in Views and Controllers *(you know how in .NET Core's MVC Controllers have IActionResult? This is pretty similar to that, except the return part's separated here.)*
* **Models** - app/Models
  * (Manual) - go to Models folder and create a file there. You need to add other stuff like namespace and A LOT of other required stuff, but like, w h y . . . ? When you have...
  * (Fancy/Best) - Terminal -> 
* **Migrations** - database/migrations 
* **Seeding** - database/seeders

## Laravel Programming Concepts Cheat List
---
* **Wild Cards** - Similar to asp-route-id
* **Route Constraints** - "->where('param', 'regex stuff here')", useful for validations
* **Debugging - dd** - Shows you what's passed in
* **Debugging - ddd** - Detailed debug info
* **Directives @** - oh hey, it's like the front-end of .NET Core except you have to put them at the start and end of something like a foreach
  * *@php* can sometimes be useful if you can't perform stuff on the controller or route
* **Request & Query** - Useful for search functions

## Relevant CLI commands for Laravel
* **php artisan serve** - run the app locally
* **php artisan make:migration name-of-migration** - add migration
* **php artisan migrate** - migrates the latest
* **php artisan db:seed** - seed
  * **php artisan migrate:refresh** - can be useful if you suddenly add/remove data in the seed
  * **php artisan:migrate:refresh --seed** refresh && seed

## Useful extensions
* **PHP Namespace Resolver** - Really useful for importing libraries and classes that act like VS' auto-fill feature
* **PHP Intelephense** - Good for PHP dev in general