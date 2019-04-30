---
layout: post
title: Enterprise Grade Home Networking
---

Most people would consider 'home networking' to be comprised of the combo unit from your ISP and a WiFi extender for that one room that is a deadzone otherwise. Not me.

> Just for the sake of disclosure, *nobody paid me to write this* and *I am not putting in any referral links*. I just want to spread the word for a product I really like using and encourage people to learn about networking.

### Networking 101

Before I dive into the intricacies of this topic and my home setup, I want to cover the basic concepts you will need to know in order to understand what follows. This is in no way a complete guide, but there should be enough information to help make the topic easier. There is plenty of content online if you want to know more and I might write a blog post about detailed networking.
#### Modem

A [modem](https://en.wikipedia.org/wiki/Cable_modem) is the entry point into a local network. Usually, the combo box ~~given by~~ you rented from your ISP has a modem inside of it. Some people, like me, choose to buy their own standalone modem; which is cheaper long term than renting from the ISP.

Most homes now will be using a cable modem, which converts the coaxial signals from your ISP to be sent over ethernet to your router. This is often labeled as the [Wide Area Network](https://en.wikipedia.org/wiki/Wide_area_network) (WAN) port on your router and/or modem.

#### Router

A [network router](https://en.wikipedia.org/wiki/Router_(computing)) routes packets. Not to be confused with the machine for woodworking, the [router](https://www.dummies.com/programming/networking/network-basics-routers/) we are talking about directs packets to the 'next hop'. This is also not to be confused with what most people mistakenly call a 'router' or '[wifi-router](https://en.wikipedia.org/wiki/Wireless_router)'.

The colloquial 'router' is actually a router, switch, and wireless access point all in one. The combo unit I keep referring to from your ISP is most likely a modem, router, switch, and wireless access point all bundled together in a monolithic box. As with the modem, the actual nitty-gritty details are not important. The key takeaway is that a proper networking router just sends packets on their way to the destination.

#### Switch

A [network switch](https://en.wikipedia.org/wiki/Network_switch) switches packets from one port to the other, usually with some clever tactics. Generally speaking, a switch does not understand much about the network, it just knows that each port goes to certain [mac addresses](https://en.wikipedia.org/wiki/MAC_address) (think device ID) and that packets that ask to go to that device should go on a certain port to get there.

A switch is very easy to spot on a combo unit, as it us usually a brightly colored strip of ethernet ports. Most combo units obfuscate the router behind these ports, so they are usually label as [Local Area Network](https://en.wikipedia.org/wiki/Local_area_network) (LAN) ports. Meaning any device you plug in one port can talk to another device in a different port.

#### Wireless Access Point (AP)

A [wireless access point](https://en.wikipedia.org/wiki/Wireless_access_point) (AP) communicates over WiFi to your wireless devices such as a phone. This AP can be a separate device, but for most people it happens to live inside of that combo box from before. Usually, the AP part of a combo unit can be spotted by the antennas sticking out of the box.

#### DHCP

[Dynamic Host Configuration Protocol](https://en.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol) (DHCP) is the way that your device gets a [IP address](https://en.wikipedia.org/wiki/IP_address) to talk on the network. For some really big networks, they use a separate DHCP server. Your home network can run just fine using the DHCP server baked into the router.

### Setup

<amp-img width="800" height="320" layout="responsive" src="/assets/network-post/all-good.jpg" alt="A screenshot of my Unifi dashboard"></amp-img>

I decided to go with [Unifi](https://unifi-sdn.ui.com) by [Ubiquiti](https://www.ui.com) as their products are reasonably, and competitively, priced as compared to similar solutions. Seeing as I live in a generic suburban home with two floors and a basement, having just one typical AP would not cover the house perfectly. Thanks to the fact that most Unifi APs are ceiling or wall mountable, I can put just one in the ceiling on the second floor near the middle of the house and get full bars everywhere.

People have suggested I get a mesh network system like [eero](https://eero.com) or the [Google Wifi](https://store.google.com/us/product/google_wifi?hl=en-US). I would be spending more and not have access to the powerful features of the Unifi SDN. The barebones setup of a USG and AP AC Lite is $210 or cheaper if Amazon has a small sale. 

<amp-img width="620" height="130" layout="responsive" src="/assets/network-post/gear.jpg" alt="A screenshot of the unifi gear I have"></amp-img>

While I have 3 things from unifi (USG, AP AC Lite, and a switch), you can get away with just and AP if you want to upgrade from the AP inside of a combo box like I did at first. I would recommend the approach I took, which is to start off with just an AP and slowly introduce more products as you see fit.

#### Rollout

For me, as I stated, I just started off with the AP to try and improve the coverage in the house and see if there would even be a noticeable impact. As it turns out, there was a pretty noticeable improvement.

For the controller software, I initially loaded it onto a [Raspberry Pi](https://www.raspberrypi.org) which did a great job and is all most people need when not running it commercially. If you want to do this at home, there is a [great step-by-step guide](https://community.ubnt.com/t5/UniFi-Routing-Switching/Step-By-Step-Tutorial-Guide-Raspberry-Pi-with-UniFi-Controller/td-p/2470231) on the forums of exactly how to do that.

After about 6 months of just having the AP hooked up to a combo box, I decided that it was time to upgrade and get access to all of the features I was missing out by not having a USG.

The biggest hurtle for most people is going to be transitioning to the Unifi Security Gateway (USG) which is primarily a router and firewall combo. Correctly replacing an existing combo unit with a router is not always an easy task. Although, if you are not that confident in your networking skills yet, a simple network setup is easy to get up and running.

The SDN software is pretty straightforward and intuitive as long as you have some basic knowledge about network topology. This includes setting up the correct IP ranges and making sure the DHCP settings are correct.

<amp-img width="800" height="320" layout="responsive" src="/assets/network-post/docker.jpg" alt="A screenshot of the unifi controller running in docker"></amp-img>

Shortly after I got the USG, I also got a [Synology NAS](https://www.synology.com/en-us) and moved the controller from the Pi. (which now runs [pi-hole](https://pi-hole.net)) Which helped improve performance and reduced the risk of SD card death.

Finally, I went and got the switch to live in the basement where the house ethernet runs converge. This allows me to better monitor traffic as it goes throughout the house and provides power to the AP.

#### Controller

<amp-img width="800" height="206" layout="responsive" src="/assets/network-post/status.jpg" alt="A screenshot of the basic network status"></amp-img>

The Deep Packet Inspection (DPI) that the USG does is also a wonderful feature. You can see the type of data being sent both throughout the different networks in the house and to the internet.

<amp-img width="1020" height="257" layout="responsive" src="/assets/network-post/dpi.jpg" alt="A screenshot of the detailed DPI overview"></amp-img>

If you want a broader look at the traffic, you can click into the insights. This will bring up the traffic usage across various categories. You can bring up the per-client usage in each respective category if you would like.

<amp-img width="360" height="480" layout="responsive" src="/assets/network-post/device-dpi.jpg" alt="A screenshot of the detailed DPI for a device"></amp-img>

If the broad view is just too broad for you, you can click on any device on the network and see the same chart, but with only the DPI data for that particular client. This is especially helpful if you want to see what a particular client is up to.

In the example above, I used my phone as it clearly shows the various items going on. You can see Google APIs because I use Google Photos, then YouTube for video watching, and the various other Apple services.

<amp-img width="917" height="524" layout="responsive" src="/assets/network-post/clients.jpg" alt="A screenshot of the clients list on my home network"></amp-img>

Lastly with the controller in terms of useful data, there is the client list. You can see the IP address, the network that it is connected to, the uptime, and the data usages. They recently also added the concept of 'wifi experience' which seems to be a metric that looks at how the traffic quality is.

### Final Thoughts

I want to wrap up by saying that, while I will go on about how useful the Unifi setup is (and will write more blog posts about it) this setup is not for everyone. For example, my less tech-savvy friends will not be able to get this setup working at home, so I just point them to some other solution that best fits their needs and is easy to maintain.

My only hope is that you start to think about what your home network can do for you, as most consumers do not make the most of their hardware.