---
title: "Cli"
date: 2022-09-14T13:49:51+02:00
draft: false
tags: ['laravel']
---

[Back to Home]({{< ref "/laravel/summary.md" >}} "Go Back.")

# Attention
This is not a complete list.

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
* ``make:controller name-of-subfolder/nameofController`` - make a controller