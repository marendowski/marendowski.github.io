+++
title = "The making of luft"
date = "2024-08-22"
tags = ["technical", "linux"]
+++

How I made my second real project and what problems I had to overcome.

<!--more-->

![air](air.jpg)

[link to the Codeberg repo](https://codeberg.org/bogdan-the-great/luft)

## The inspiration

I wanted to write something small for [wlroots](https://gitlab.freedesktop.org/wlroots/wlroots/). At the moment I was also adding more complexity to my daily workspace, per [Keep it simple, not simpler](../simple). I lived without a notification daemon for about a year because I didn't see the need, I always turn off notifications anyway. I started using [mako](https://github.com/emersion/mako) because [fnott](https://codeberg.org/dnkl/fnott) was too fancy for me. Then [sewn](https://codeberg.org/sewn) with [choc](https://codeberg.org/notchoc) created [drwl](https://codeberg.org/sewn/drwl) which I wanted to use in my soon-to-be wlroots project. While poking around in mako and fnott, I saw a lot of complex code and wondered if I could write an even simpler notification daemon, since I only needed it for a few small scripts.

## The process

I had to learn Wayland-specific stuff first. [The Wayland Book](https://wayland-book.com/) is great for an introduction, also watching and doing the ["zero to window - wayland client"](https://www.youtube.com/watch?v=iIVIu7YRdY0) to reinforce this knowledge.

Then I started writing a base client that would resemble a notification, but I made it a `toplevel` (normal application window) so it would behave like a normal window. Then I started looking for programs that were built on similar principles. I found [wtw](https://codeberg.org/sewn/wtw), which showed me the `zwlr_layer_shell_v1` protocol, which was made for this purpose (it basically creates a layer shell on which you can create surfaces that do not follow the normal client rules, e.g. cannot be moved and must be displayed on top of all windows, etc.).

After some time and using [drwl's example](https://codeberg.org/sewn/drwl/src/branch/master/example), I was able to create a simple window that was drawn over other clients.

## The burnout

After that, I had a burnout - nothing in this project was fun to write and I didn't do much for about two weeks. There was a lot going on in my life at the time, so this project seemed trivial and I even considered dropping it. At the end of the second week of burnout, I went on vacation and came back like a phoenix - ready to finish what I had started.

## The good ending

At this time I thought of it as the [herbe's](https://github.com/dudik/herbe) wlroots port. I tried to follow all the design principles of herbe and aimed for feature parity with it. I also started doing something new - writing a TODO list in a markdown file. This made it very easy to come back after a few days, and I always knew what to work on next. This whole part was the best of the whole process, where I had fun adding something every day and was now on a clear path to the end. After implementing most of the features of herbe, I was confident enough to release it in a repo. I wanted to make the README pretty similar to herbe's when I saw this:

```
Wayland port by muevoid
```

I didn't scrap this project, and I'm still grateful for the learning opportunity.
