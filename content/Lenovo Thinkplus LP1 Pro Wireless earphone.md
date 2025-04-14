---
title: Thinkplus LP1 Pro dead case
draft: false
tags:
  - repair
  - audio
cssclasses: 
aliases: 
date: 2022-12-30
---
Today's patient is:  
-Lenovo Thinkplus LP1 Pro Wireless earphone  
  
Trouble:  
-the Left bud is not turning on.  
-the Charging case is not turning on.  
  
Diagnose:  
After painstakingly disassemble the case, we found sign of corrosion on the charging case body. upon further inspection, turns out the battery is corroded and kicking the protection on the charging circuit thus preventing the voltage to be delivered.  
  
after disconnecting the faulty battery, the case happily lit up when charged with usb C cable. a 5V output also presented on the pogo pin connecting the circuit to the buds. with this we can conclude that the charging circuit is still working.  
  
next, we disassemble the left earbud. glued using some kind of hot glue, the bud disassembled easily by praying between seams using fingernail. inside we have a bluetooth/charging circuit, a lipo battery, and a speaker.  
  
checking the voltage from the battery gives us 1,01v. too low for a lipo. looks like the battery is overdischarged with no way to return. consulting the code on the battery body to google, looks like we have an ultra thin 450911 30mAh lipo battery. it has 4.5mm x 09mm x 11mm dimension and available from alibaba on the bulks.  
  
after disconnecting the battery and feeding the buds using 3.7V direct power supply, we found that the bud is still working. connection via bluetooth and playing audio still works too. replacing the battery should be fine.  
  
after googling on local market we found similar product on tokped. but the dimension is 4mm x 09mm x 09mm. maybe its fit? since it cost only 12k rupiahs, we take 5 for a spare.  

after waiting for a week, the battery for the left earbud has arrived. now we just need to carefully solder the battery to the earbud circuit carefully.  
  
to minimize short circuit possibility, always cover the other terminal wire and connection when not in use. since this mini battery has no protection circuit, one touch of reverse polarity short, and it would puff a magic smoke.  
  
after soldering the negative and positive wire to the battery, now it's time to test the result. after pressing the capacitive pogo pin for 5 second the bud gives us a blinking green light. after that, testing the Bluetooth function is also working. perfect!  
  
whats left is replacing the charging case battery and reassemble the unit. unfortunately, the lipo battery that we bought are too big for the case. but the case should still works without the battery. and the buds can still get charged.  
  
when the bud put into the case, it will detect 5V on its connector and the bud will turned off automatically and enter charging mode. and when the connector detected 0V, the bud will turn on and pair to whatever device its already paired to.  
  
the voltage comes from the battery and controlled using a reed switch that detecting magnet presence. the magnet tucked to the top case and moving close to the switch by opening/closing the case.  
  
so without the internal battery, the bud wont turned off when placed into the charging case unless its plugged into a charger. and also, when not charging the bud will automatically turned on even without opening the case.