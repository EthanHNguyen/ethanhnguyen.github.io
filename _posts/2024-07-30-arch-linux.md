---
title: 'MacBook -> Thinkpad + Arch Linux'
date: 2024-07-30
permalink: /posts/2024/07/30/arch-linux/
tags:
---
I have been a Apple user for the last 6 years. Here are a list of products I own:
- MacBook Pro
- iPad Pro
- iPhone
- Apple Watch

I've really enjoyed my experience with Apple. I love how "everything just works" and the tight integration between software and hardware within Apple's ecosystem. I can respond to text messages on any device and my photos are automatically synced to iCloud. However, I have become annoyed with how tight Apple's ecosystem has become. As my hardware stack has aged, I have realized that Apple has increasingly moved to using planned obsolescense in a scheme where it is hard (and expensive) for the user to repair instead of buying a new device (see [Louis Rossman](https://www.youtube.com/watch?v=NVAmnV65_zw). For example, my 6 year old MacBook Pro has started showing its age. On my previous laptops, I have been able to perform basic hardware maintenance (replacing thermal paste, cleaning the fans, etc) and make hardware upgrades (SSD, RAM, etc). However, with Apple, some of these tasks are now impossible. The practice of planned obsolescense is expensive and harmful to the environment. So, in the last year, I've begun looking for a different tech stack.

I use my computer to browse the web and build web apps, so I only need a basic device. Any laptop from the last 5 years should be able to handle these tasks. Here are a couple requirements I had:
- 15" inch screen 
- Quad-Core Processor
- 4-5 hours of battery life
- Easy to repair (can upgrade SSD and RAM)

With these requirements, I bought a second-hand Thinkpad T580 from eBay for $130. A lot of companies lease Thinkpads and sell them after 4-5 years, so these laptops and their parts are widely available on the market for low prices. When the laptop arrived, it looked almost brand new and had less than 100 cycles on the battery. Also, the keyboard did not disappoint! 

For the operating system, I wanted something lightweight and flexible enough to tailor the OS to my needs. Arch Linux was an ideal choice. I've kept Windows 10 dual booted just in case an application does not run on Linux.

In the last couple days, I've really enjoyed using Arch Linux! Arch basically only ships with the Linux kernel and a package manager called pacman. I love having the flexiblity to add exactly what I need and nothing more. I am not beholden to some corporation. I can build and maintain my system however I want. 

One unexpected benefit is that I feel more connected to my operating system and the FOSS world. I have found that working on Arch makes me more motivated to write software for fun. On MacOS, everything felt too locked down, but on Arch Linux I feel free to read and modify source code with other programmers. For example, I wanted always wanted my laptop to stop charging at 80% to better protect my laptop's lithium ion battery. In MacOS, this required some pretty complex code to modify the SMC (feel free to read this battery management app - [AlDente](https://github.com/AppHouseKitchen/AlDente-Charge-Limiter/tree/master) source code). However, Linux has a  nice interface where you can write an integer between 0 to 100 to a file to set charge limits (see [TLP](https://linrunner.de/tlp/settings/bc-vendors.html)).

It's early days for my transition to Arch Linux and I expect a lot to change. I am wary of whether apps are supported on this distro. I mainly use webapps and avoid propietary software where I can. However, I have run into situations where Linux is not supported. For example, to take my AWS certification exam, I needed to be on a Windows or Mac system ([PearsonVue Requirements](https://home.pearsonvue.com/Standalone-pages/System-requirements-ITS.aspx). To progress on my learning curve, I plan to daily Arch and read "How Linux Works, 3rd Edition: What Every Superuser Should Know" by Brian Ward.

If you have any recommendations for transitioning to Arch, feel free to email me. I'll share on my blog anything useful I learn during my journey.
