---
title: Gamen Titan III dead rows
draft: false
tags:
  - repair
  - keyboard
  - mechanical
  - hardware
cssclasses: 
aliases: 
date: 2024-05-18
---
lo and behold! another mechanical keebs!  
  
this time, its Gamen titan III "true" RGB with detachable wire. i got this one for cheap (only 60k) on greenstore with same symptom as its brother (titan II) last time.  
  
the build quality of this keebs looks better than its brother. using thick metal as a mounting plate, this keebs feel solid. no wonder the price is still good.  
  
without further ado, lets disassemble and remove some leds. after removing the screws and the bottom cover, whats left is the pcb and mounting plate.  
  
at a glance, this look like a soldered switch pcb. but after carefully pulling out a switch, turns out its hot-swapable. good.  
  
first step to check the location of the column track. using multimeter in continuity mode, just probe the switch hole one by one till you found a beep.  
  
after making sure the column track is okay, next is to check the track continuity from the column to microcontroller. again, use the multimeter in continuity mode. okay, found the beep.  
  
if the track is good, lets look at the leds. measuring using diode mode we can check the forward voltage of the leds and determine if its okay or not. ...or, we can just look at that burnt mark and corroded pin on the led.  
  
without further ado, lets pry that one and voila! it works! this time, only one bad led so we can hope to replace this with another led and get some profit.  
  
from the body it looks like 6030 smd led with common + at pin 3 with dome like reflector. rgb like this retail from 500 silvercoin to 2000's.  
  
searching on green store we found a match. rgb led smd 6028, it even has keebs keyword on it. but the price ...  
  
well, thats just how business works...