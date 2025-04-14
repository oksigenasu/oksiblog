---
title: Gamen Titan II Keyboard dead keys
draft: false
tags:
  - repair
  - keyboard
  - mechanical
  - hardware
cssclasses: 
aliases: 
date: 2024-05-01
---
todays repair is this:  
el cheapo mechanicaru keebodo Gamen Titan II. i bought this from green shop for 100k. since i need a reference for a future project, and a friend of mine refer me to this.  
  
the seller advertise this as good condition with a few key not registering any input and couple of dead LED. in my experience tinkering with membrane keebs, this problem usually due to broken traces or stuck keys.  
  
upon inspection, a column of keys not working and a couple of LED row are lit strangely. other than that all function are normal.  
  
after painstakingly pulling the key caps and removing the switches, what is left is a barebone PCB with a controller, tons of LEDs, and tons of diodes.  
  
on a keyboard like this, the diodes are used for something called Key Rollover (KRO). to put it simply, its the ability of a keyboard to register multiple input correctly.  
  
a 2KRO keyboard can only detect 2 keypres simultaneously. n-KRO keyboards can detect n-keypress simultaneously. so more diode equals to more keypress.  
  
back to the repair. testing the traces with continuity tester found no broken traces. so the problem must be somewhere else. and since a couple of LEDs behavior are sus, lets continue there.  
  
an LED basically is a diode that glow when a current goes through. and like diodes, when the polarity is reversed, it block the current.  
  
common problem with diodes are either they cant let a current passthrough, or they cant block or leak the current in reverse polarity. for this, we can check the resistance of the LEDs. one by one.  
  
on this keyboard, a normal LED gives resistance around a couple of Mega Ohms when checked in reverse. anything lower than that is sus. and we found a sus on the dead column.  
  
after found more sus and removing them, lo and behold! a working keyboard! (with more dead LEDs).  
  
anyway, thats it for today. if you like and enjoy this, dont forget to like and subscribe.  
  
..wait, this is not youtube.