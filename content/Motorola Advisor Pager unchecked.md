---
title: Motorola Advisor Pager unchecked
draft: false
tags:
  - repair
  - hardware
  - iot
cssclasses: 
aliases: 
date: 2024-08-04
---
Today's patient is this:  
unchecked Motorola Advisor Pager  
  
i saw this thing sold by a salvager on facebook with a caption "unchecked" for 50k rupiahs. having a nostalgic value with this device, i thought "i got to have it".  
  
My dad used to have this kind of pager, and I fondly remembered how my mom would use a public payphone to call the operator just to send a message to my dad to pick us up.  
  
after the golden era of public payphone, i still have a fond memory with this thing in my school days. i used it as an ultra loud super cool alarm that wake the shit out everybody at the dormitory. even my sister still use it after me.  
  
enough with the nostalgia.  
  
the device came within a week, with near mint condition minus the "unchecked" (meaning dead) and some debris inside the screen. surprisingly, this device can be opened without needing a single screwdriver! neat!  
  
scouring the internet, i finally found the schematic for this device. and after a couple of probing, i found the voltage (B++) from the power supply IC (U4) was missing. turns out, an inductor's wire was disconnected from its pad and not directing the voltage to the other IC.  
  
Alhamdulillah, i am able to connect the wire using solder. and after plugging the battery, i hear a couple beep. checked!  
  
there are a lot of tutorial on the internet on how to repurpose this device other than being an alarm. like using raspi to send POGSAC message, using arduino piggyback to receive message from other wireless, or reprogram the screen with DOS-old application.  
  
well, thats for another time...