---
title: "NOMAD Laptop"
author: "pat/patcybermind"
description: "an open source semi modular laptop"
created_at: "2024-06-29"
---

total hours: 55

## june 29th:
4 hours

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

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/5dcaa516637028705314b054f8e08150483699e8_v1_art.png)

## july 30th:
4 hours

I did some more research im looking at what batteries im going to use. At the start i wanted to use 18650 cells but they are 1.8cm thick which is far too much. i want the laptop to be under 1.6cm thick total so instead i think im going to go for some 7mm lithium ion pouch cells probably 3 of them in series or maybe 4. After that i also dissasembled an old 2013 thinkpad to see if it has an embedded display port display and i think it does
so I think its a pretty good option to use as a cheap display for the laptop. It could be better but im not very picky when it comes to screens as all my displays are average or under average. Other than my phone.
![image](https://github.com/user-attachments/assets/90a63b04-9371-4ebc-9fe4-40b8f9769fe8)
something like this

## july 7th:
10h
back from camping
I started placing stuff in the schematic but im still figuring out what to connect ot waht pins because beleive it or not there are 260 pins in the conector. I'm prob not even going to use half of those but i still need to understand what they do. Lattepanda actually has decent documentation about this and they have a discord that ive joined and also i read this blog? where this guy was making his ownn carrier board and i followed what he did for finding your trace settings and setting up the drc so you have the right impedance but unfortunuately the guy never finished it so it didnt go far. Theres also this guy on youtube who made a carrier but he didnt go super in depth. Ive been going through the example carrier board that is provided in their github but im trying to make sense out of it because they use different pages and ive never used different pages also idk why they have these blocks rn so yeah i still need to do some mroe googling and chatgpting. 
![image](https://github.com/user-attachments/assets/249658f2-4973-4325-af33-5cadeed54dd0)

I also exported the example board to jlcpcb with the settings i plan on using for the final board and this is the price but keep in mind this doesnt include pcba which ill be using.
Its about what i estimated earlier so with pcba it should be around 90usd ideally less.
S![image](https://github.com/user-attachments/assets/70a10e22-4185-4d1d-bbbd-e83c047bf576)

## july 8th:
7 hours

Today i finished the schematic part of the main pcb. I say main pcb because there will be a second pcb that controls rtl-sdr usb connection sends custom touchpad hid info to the lattepanda mu and keyboard keystrokes and handles the batteries. Disclaimer i did base myself off of the lite carrier board example. The mainboard has 4usb connections 2 usb3 A ports 1 usbc 2.0 port and one internal (broken out to pins) usb 2.0 The purpose of this is to let me make a second pcb (because i want to keep this mainboard pcb under 10cmx10cm to keep the cost down as much as i can)  that aside from doing all of what i said earilier will also act as a usb hub to add 2-3 more usb ports 2 of them staying inside the laptop one going to the rtl-sdr inside the laptop and the other one going to human interface devices i.e. the touchpad and keyboard The reason i have to use a usb hub is because the n100 intel usb controller only allows for 4 "root" usb connections. This pcb will use an rp2040 in hid mode.

![image](https://github.com/user-attachments/assets/3a8c4d2a-f6e0-4241-97a5-c9cb22bccad8)
Have not been placed yet but they are now inside the pcb editor ready to be placed.




![image](https://github.com/user-attachments/assets/29a8f1e8-9572-4859-b0a4-66394c966af9)
usb schematic sheet

## july 9th:
7 hours:

Today I basically placed most components where they should go and whats left is mostly just waiting to be placed on the board but already togheter i.e. boost converters are togheter but not on the board. I also had to edit the schematic a little bit because i realisd some things were missing or had to bbe modified like the power button, it needs to be a connector and not a button. Also i messed up and put everything on the wrong side and had to restart though lucky i was only like 2 hours in at the time so it wasnt that bad. basically the problem was that i forgot this was going to go upside down and i want the usb ports to be on the right of the laptop and the lattepanda mu and its ddr slot need to face the display so i can connect the embedded display port fpc cable dirrectly to the mu. So yeah i basically did it flipped the first time. The reason it has to go upside down is that while the chassis will most likely be 3d printed as of right now. I say most likely because I am considering making it entirely out of aluminum maybe press formed. But say it does end up being 3d printed, the bottom will have a solidaluminum sheet as flush and seamless as possible with the rest of the chassis. This will act as a huge heatsink and heatspreader which if anodized should be able to dissipate around 70 watts and if not it should still be able to dissipate around 40 watts which will definitely be enough. You might be concerned though that the heat will stay in one spot and so am I so between the aluminum and the mu i will also add an intermidiary smaller sheet of copper just to get the heat more spread and less concentrated. Aditionally the 70w and 40 w figures i gave earlier are assuming a 30x30cm piece of aluminum under 60c, if the temp goes over 60c then itl disspate even more heat but i dont want it getting too hot because a laptop who can give you burns is a bad laptop. And you might be wondering what the difference between anodized aluminum and normal aluminum is when it comes to getting rid of heat? As it turns out anodised black aluminum radiates heat in infrared emmisions over 20 times more than normal aluminum. 0.0x vs 0.8x-9x emmisivity. So its basically like one of those radiators they use in space. Pretty cool math.

![image](https://github.com/user-attachments/assets/002a936a-11ac-4210-a4ea-bc44ce83f45a)
As you can see most things are aglomerated or on the board already. I'm going to route the high speed traces before i place mostof the other components too since thats the most important thing to get right.



## july 10th:
3 hours
went fishing today so didnt have nearly as much time but i finished placing everything where it should be and now im finishing the setting up of the board settings because in kicad, when you are making impedance matched traces and differential pairs and stuff, you set up the board to havve 4 layers etc and then you set up the nets and tell them the right sizes so you get everything right and the impedance is right. Also ive started making sure to commit my kicad files everytime i update because im scared ill mess something up later and wont be able to come back. Also cool thing i learnt is that kicad seems to also have a version control system system but im still just commiting with vs code because why not.

<img width="172" height="332" alt="image" src="https://github.com/user-attachments/assets/b0378170-832f-4088-9d0b-e81b331863b7" />


## july 10th:

<img width="1197" height="661" alt="image" src="https://github.com/user-attachments/assets/e50746e6-dfc6-4f02-840a-a35be9396b7c" />

## july 17th:
6 hours:

