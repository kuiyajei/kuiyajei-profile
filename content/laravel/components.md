---
title: "Components"
date: 2022-09-19T03:42:46+02:00
draft: false
---

[Go Back]({{< ref "/laravel/summary.md" >}} "fuc go bac") <br/>

<a href="https://youtu.be/MYyJ4PuL4pY?t=4099" target="_blank">explanation or something</a>

slot may refer to the blade.php prefix's name with one {{ $slot }}  
in other files it is used with the component `<x-viewName></x-viewName>`

slot may also have multiple slots, but the other slot(s) must be named  
you may only access that other slot within the initial component  
`<x-viewName><x-slot:title></x-slot></x-viewName>`  
`<x-viewName><x-slot name=''></x-slot></x-viewName>`  