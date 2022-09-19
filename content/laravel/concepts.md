---
title: "Concepts"
date: 2022-09-14T13:49:57+02:00
draft: false
tags: ['laravel']
---

[Back to Home]({{< ref "/laravel/summary.md" >}} "Go Back.")

## Laravel Programming Concepts & Terminologies
---
* **Wild Cards** - Similar to asp-route-id
* **Route Constraints** - ``->where('param', 'regex stuff here')``, useful for validations
* **Debugging - dd** - Shows you what's passed in
* **Debugging - ddd** - Detailed debug info
* **Directives @** - oh hey, it's like the front-end of .NET Core except you have to put them at the start and end of something like a foreach
  * *@php* can sometimes be useful if you can't perform stuff on the controller or route
* **Request & Query** - __Useful for stuff like search functions__
* **Layout & Sections** - GODDAMN my bRIan not handle dis. This thing deserves its [own page]({{< ref "/laravel/components.md" >}} ":)")
  * In the layout:
    * ``@yield('matching-content-name')`` this is where you want the view to be displayed at when the view extends the layout
  * In the View extending the layout: 
    * ``@extends('layout-name')`` put this on the very top
    * ``@section('content-name')`` and ``@endsection`` then wrap that around the content you want as a section
  * **Blade Components** - useful if you want to pass in stuff...? <a href="https://www.educba.com/laravel-components/" target="_blank">[link]</a>