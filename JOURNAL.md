---
title: "NOMAD Laptop"
author: "pat/patcybermind"
description: "an open source semi modular laptop"
created_at: "2024-06-29"
---

total hours: 20

## june 29th:
So ive already done a lot of research but today i finally made the repo and im ready to start working on it. Ive done about 20 hours of research so far. Basicly this idea had started a while ago when i learnt about single board computers and was looking to buy better options and cheaper options that just a normal raspberry pi because they are pretty expensive and could be better. This was around the time where i wanted to get more into open source digital fpv and also into 3d printing and well for both of those you need well you dont need but its recomended that you have a sbc like a pi or and for open source fpv the alternative is a bit more expensive. So i read stuff, read articles etc. Saw that most sbc manufactuers also make compute modules or SOMs (System On Module)
and also there is a lot more variety that just pis for example the radxa rock lineup based mostly on
rockchip chips. After reading about what they could do i was like huh why hasnt anyone made like
a laptop with one of these. Turns out 2 weeks later id get recomended bryan's youtube videos
and i was like oh wow. Turns out it is fairly doable. He used an arm rk3588 based SOM. Its pretty
powerfull for a SOM and its twice as efficient as a pi. Trust me i got an sbc (rock 5c) based on it
and wow its crazy how much less electricity it consumes like it straight up stays way cooler.
Anyways i decided on using a lattepanda mu. Why? because as far as i know no one else has made
an x86 laptop of this type and the lattepanda mu is still fairly efficient and should give usable battery life on a laptop. Also because it should be slightly faster i beleive because although the n100 and the rk3588 have similar benchmark scores, the rk3588 has 8 cores and the n100 only has 4.
each core of the n100 is close to 2 times faster which means that for single threaded tasks like loading things ie loading a website the n100 should be faster. And this laptop will be made for
light work like coding and browsing so thats perfect.

#### Goals:
youtube battery life: 6 hours 
thickness: under 1.6cm
modularity: m.2 slot, mxm (mobile) gpu, compatible with n305  lattepanda mu, extra pcie, 
repairability / workability: ideally make so you dont have to dissasemble the entire laptop to get to 1 part ex batteries
peripherals: internal room for pcie fpga and an sdr and other stuff like that
ports: usb A, usb C, hdmi, microsd


Also i spent the last 30 minutes working on this concept art lol
I like when people make concept art to visualize somthing so thought id do it too
(https://hc-cdn.hel1.your-objectstorage.com/s/v3/5dcaa516637028705314b054f8e08150483699e8_v1_art.png)
