---
template: main.html
---

# Air Gradient

Some time ago,  I saw Jeff Geerling's video about how your home's air could be making you sick.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Cmr5VNALRAg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

I decided I had to have one, but I couldn't source the parts. When he posted the video, it became almost impossible to source these parts overnight. I waited until [airgradient started selling the kits](https://www.airgradient.com/diyshop/) and you could build them as an afternoon project. It took me roughly an hour and a half to put together with mediocre soldering skills.

## Following Geerling's Footsteps

Flashing the airgradient was almost to easy. Install and launch the [Arduino IDE](https://www.arduino.cc/en/software). Select the board, install the required packages in the package manager. Connect the ESP using **a cable that has all four strands of wire**, because I tried to use one that had no data lines >:(

## Let's Improve It

At the time, I already had grafana and a whole 'nother prometheus stack built into my [home-cluster](https://github.com/kashalls/home-cluster). I just needed a way to take the stats from the airgradient and shove them into promtheus.

I hit up my friends at [k8s@home](https://github.com/k8s-at-home) and we spent the night working on migrating the entire library from relying on an external container to cache stats to letting prometheus access the device itself over the local network. See my [pull request](https://github.com/geerlingguy/airgradient-prometheus/pull/4) that I created on this.

Apparently, Geerling liked it so much I got a shoutout :O

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">This is the kind of thing that makes me so happy to develop with open source. I put something out there, someone takes it and makes it like 20x better with one PR: <a href="https://t.co/lnTw8ozk6c">https://t.co/lnTw8ozk6c</a> <a href="https://twitter.com/hashtag/opensource?src=hash&amp;ref_src=twsrc%5Etfw">#opensource</a> <a href="https://twitter.com/hashtag/thanks?src=hash&amp;ref_src=twsrc%5Etfw">#thanks</a> <a href="https://twitter.com/hashtag/payitforward?src=hash&amp;ref_src=twsrc%5Etfw">#payitforward</a></p>&mdash; Jeff Geerling (@geerlingguy) <a href="https://twitter.com/geerlingguy/status/1437625199181107200?ref_src=twsrc%5Etfw">September 14, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Honestly, this was the highlight of my week.

## Okay, We Can Stop

We even went a step further and, in an attempt to preserve commit history, created another fork called [airgradient-prometheus-sensor](https://github.com/Kashalls/airgradient-prometheus-sensor) with the hope of streamlineing the software for prometheus. It works exactly the same, but looks different.