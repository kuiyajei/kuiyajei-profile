---
title: "Cheat Sheet / Summary"
date: 2022-09-12T07:49:34+02:00
draft: false
tags: ['laravel','summary']
---

[Back to Home]({{< ref "/" >}} "Back to Home")

# This not a full guide. 
Not everything will be explained in full detail.

<!-- ![floppa](/laravel/images/floppa_poly.png)  <br/> -->

These notes are based on <a href="https://youtu.be/MYyJ4PuL4pY" target="_blank">TraversyMedia's Laravel Crash Course</a> | Uploaded: Apr. 26, 2022  
and a <a href="https://www.udemy.com/course/laravel-build-complete-inventory-management-system/" target="_blank">Udemy Course</a>

*my notes have references to .NET Core so this might not actually be helpful*

## List of other pages related to laravel found in this site.
* [Laravel > Structure]({{< ref "laravel/structure.md" >}} "Laravel > Structure")
* [Laravel > Concepts]({{< ref "laravel/concepts.md" >}} "Laravel > Concepts")
* [Laravel > CLI]({{< ref "laravel/cli.md" >}} "Laravel > CLI")
* [Laravel > Themes]({{< ref "laravel/themes.md" >}} "Laravel > Themes")

## Installation for Windows
---
Software you need...
- something to run Linux commands, so install GitBash (the documentation tells you to get Docker but don't mind that)
- Composer
- to run the following in a terminal - assuming you're going to use Laravel for quite a while and it's not just a one time thing:
  ``composer global require laravel/installer``.
  Then in the directory where you want to work on, open a terminal there and ``laravel new name-of-your-app``. If it's the latter, then do this instead of the above ``composer create-project laravel/laravel name-of-your-app``.
- Laravel Breeze: because you'll most likely use it for simple default login/auth
  1. ) inside your project > terminal > type in ``composer require laravel/breeze --dev``
  2. ) followed by ``php artisan breeze:install``
  3. ) followed by ``npm install``
  4. ) followed by ``npm run dev`` then stop that shet in the terminal (Ctrl + C > y)
  5. ) followed by `php artisan migrate` when your DB's connected

### Importing an existing project

Assuming that you have done the initial installations and exported the files (if zipped)...
1. Open XAMPP and start Apache + MySQL
2. Databases tab > Create
3. Imports tab
4. Get ``.sql`` file  > Choose that as file to import
5. Inside ``.env`` > ``DB_DATABASE=name-of-newly-created-db``
6. Inside project file enter the following in a terminal
   1. php artisan config:cache
   2. php artisan cache:clear
   3. php artisan view:clear

### Optional but cool (stuff I'm not familiar with even outside of the regular MVC sh*t)
---
* **Faker** - I really am not familiar with this <a href="https://youtu.be/MYyJ4PuL4pY?t=3791" target="_blank">so...</a>
  * **php artisan make:factory name-of-factory**
  * **Example:** ``'title' => $this -> faker -> sentence(),``
    * sentence can be replaced by other formats found <a href="https://github.com/fzaninotto/Faker#table-of-contents" target="_blank">here</a>


### Useful extensions
---
* **PHP Namespace Resolver** - Really useful for importing libraries and classes that act like VS' auto-fill feature
* **PHP Intelephense** - Good for PHP dev in general