---
title: 10K mAh powerbanks dead
draft: false
tags:
  - repair
  - powerbank
  - hardware
cssclasses: 
aliases: 
date: 2024-07-30
---
Today's repair involves these 10K mAh power bricks. One day, the owner wanted to charge these, and when plugging in a charger, one of them went kaput. Still skeptical, they tried the charger on the other power brick and... double kill.  
  
After battling with a lot of silicone glue, we finally opened these bricks. Inside, we can see a LiPo battery and a charger controller IC. For the white one, the controller is an IP5306 charging and buck converter with auto-off and a couple of LED indicators. For the black one, the controller is an IP5508 charging and buck converter but with more amps and support for an 188 style LED display.  
  
After removing the LiPo battery connector and checking the circuit, we found that the output voltage was shorted to ground. Luckily, the LiPo battery still had some voltage and was presumably good. Most likely, the charging IC was shorted because of the bad charger. Let's pluck them out and order some replacements.  
  
The one with the IP5306 was easy to find, but the other one was only available in module form and the price was... let's just say, not quite profitable. So we had to make do with the IP5306 and quite a bit of jumper wire action.  
  
Once the replacement arrived, we proceeded to blow the replacement with a 300°C hot air gun and recheck the short. After confirming the safety, the battery was reconnected to the circuit and tested. The charging function was okay, and the indicator LEDs were perfect. Let's wrap this up.  
  
For the other one, we needed to open the datasheet to determine how the LED charlieplexing was wired. With some jumper wires and glue, we finally finished this one as well.  
  
Now we have two working power banks, albeit with downgraded specs. Well, it's better than two doorstoppers.