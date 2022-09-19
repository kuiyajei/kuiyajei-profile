---
title: "Fixes"
date: 2022-09-19T02:57:19+02:00
draft: false
---

[Go Back]({{< ref "/laravel/summary.md" >}} "getdafucoutahere")

# I fear no bug,
but ``routes``? It scares me...

Make sure everything in that *thing* is fixed. If one thing is broken there, then EVERYTHING else is broken - including the artisan CLI.

# DB Full Clean
1. `php artisan config:cache`
2. `php artisan cache:clear`
3. `php artisan view:clear`
4. `php artisan migrate`
5. You can also `php artisan db:wipe` and steps 1-4 in case you're worried about making changes and the whole thing just doesn't work for some reason.