---
title: "FAQ Fixes"
date: 2022-09-13T14:45:08+02:00
draft: false
tags: ['hugo','fix','summary']
---

[Back to Home]({{< ref "/" >}} "fuc go bac") <br/>

# Summary

If you ever encounter some basic f**k-ups while building your blog (or something similar) and you can't find the solution online, just come back here. Hugo doesn't get much attention so it's hard finding actual solutioons :(

# The ***TRUE*** FAQ regarding fixes. Make sure to look at the date, though. This might go unupdated in the future.

FAQ:
* A theme's layout might override your home page. To counter that, just make an ``index.html`` inside *your* ``layouts`` folder. If you want to go back to the home page using a link, just reference your baseURL value. 
* Page link referencing can be weird so here's a couple of things:
  * Use this ``[Back to Home]({{< ref "/" >}} "Back to Home")`` or this ``<a href="YOUR-baseURL"></a>`` to go back to your default page.
  * ... hold up still practicing 
* Static images don't work for some reason so... 
  1. ) Make a *subfolder under content* > *create another subfolder under that called 'images'*, > put your images there.
  2. ) Use the html img tag in your .md file under that subfolder (not images) to use your image. Example:``<img src="/posts/images/your-image.PNG" alt="img-description">``
  Note: the file extension is case-sensitive, meaning you might have to put ``png`` instead of ``PNG``
* True GitHub Pages deployment tutorial:
  1. ) ``git init`` your sh*t then 
  2. ) Add local repository in GitHub Desktop to make your life easier and publish it; side note - this is not a git tutorial so look into it if you don't follow
  3. ) Config your ``baseURL`` with the value of ``https://<YOUR-GITHUB-USERNAME>.github.io`` or ``https://<YOUR-GITHUB-USERNAME>.github.io/<REPOSITORY_NAME>``
  4. ) Also add ``canonifyURLs = 'true'`` inside the config or else images won't render except for the local server. Weird.
  5. ) Go to your remote repository - **make sure it's public** - and go to Settings > Pages > Source: GitHub Actions > Click the Hugo option > Commit and adjust accordingly if you want a different branch to be published.
  6. ) Done!
