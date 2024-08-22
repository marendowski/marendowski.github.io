+++
title = "I ran `sudo rm -rf /*` because I wanted to change the font size"
summary = "And I'm mad."
date = "2024-07-14"
lastmod = "2024-07-24"
tags = ["technical", "linux", "news", "rant"]
+++

Because mrmierzejewski (in [this site's theme](https://github.com/mrmierzejewski/hugo-theme-console)) can't fucking make two css files logical and has to use cryptic names and change everything everywhere while not using variables which he created to make it easier. CSS of this theme is a fucking joke, half of it isn't even used.

Yeah, it's my fault for running `sudo rm -rf /*` instead of `sudo rm -rf *`. I wanted to change the fucking font size of the headers and didn't see any effect when I changed it in the "main" CSS file, so I wanted to "refresh" the public folder. And because you can't fucking name anything logically, it was only possible to change it in `terminal-0.7something` CSS file in the middle, a fucking joke. Not to mention `animate0.7something` file with unused animations.

Don't get me wrong, this theme is amazing and I'll use it, but can't you make your CSS normal?
