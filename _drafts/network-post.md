---
layout: post
title: Enterprise Grade Home Networking
---

Most people would consider 'home networking' to be comprised of the combo unit that your ISP provided you and a WiFi extender for that one room that is a deadzone otherwise. Not me.

### Networking 101

Before I dive into the intricacies of this topic and my home setup, I want to cover the basic concepts you'll need to know in order to understand what follows. 

#### Modem

A [modem](https://en.wikipedia.org/wiki/Cable_modem) is the entry point into a local network. Usually, the combo box ~~given by~~ you rented from your ISP has a modem inside of it. Some people like me choose to buy their own standalone modem, which is cheaper long term than renting from the ISP.

Most homes now will be using a cable modem, which converts the coaxial signals from your ISP to be sent over ethernet to your router. If you want to read more into modems, you can, but this is about all you need to know for this post.

#### Router

A [network router](https://en.wikipedia.org/wiki/Router_(computing)) routes packets. Not to be confused with the machine for woodworking, the [router](https://www.dummies.com/programming/networking/network-basics-routers/) we are talking about directs packets to the 'next hop'. This is also not to be confused with what most people mistakenly call a 'router' or '[wifi-router](https://en.wikipedia.org/wiki/Wireless_router)'.

The colloquial 'router' is actually a router, switch, and wireless access point all in one. The combo unit I keep referring to from your ISP is most likely a modem, router, switch, and wireless access point all bundled together in a monolithic box. As with the modem, the actual nitty-gritty details are not important. The key takeaway is that a proper networking router just sends packets on their way and only that.

#### Switch

A [network switch](https://en.wikipedia.org/wiki/Network_switch) switches packets from one port to the other, usually with some clever tactics. Generally speaking, a switch does not understand much about the network, it just knows that each port goes to certain [mac addresses](https://en.wikipedia.org/wiki/MAC_address) (think device ID) and that packets that ask to go to that device should go on a certain port to get there.

A switch is very easy to spot on a combo unit, as it us usually a brightly colored strip of ethernet ports. Most combo units obfuscate the router behind these ports, so they are usually label as [Local Area Network](https://en.wikipedia.org/wiki/Local_area_network) (LAN) ports; meaning any device you plug in one port can talk to another device in a different port.

#### Wireless Access Point (AP)

A [wireless access point](https://en.wikipedia.org/wiki/Wireless_access_point) (AP) communicates over WiFi to your wireless devices such as a phone. This AP can be a separate device, but for most people it happens to live inside of that combo box from before. Usually, the AP part of a combo unit can be spotted by the antennas sticking out of the box.

<amp-img width="800" height="320" layout="responsive" src="/assets/network-post/all-good.jpg" alt="A screenshot of my Unifi dashboard"></amp-img>

I decided to go with [Unifi](https://unifi-sdn.ui.com) by [Ubiquiti](https://www.ui.com) as their products are reasonably, and even competitively, priced as compared to similar solutions. Seeing as I live in a generic suburban home with two floors and a basement, having just one AP would not cover the house perfectly.