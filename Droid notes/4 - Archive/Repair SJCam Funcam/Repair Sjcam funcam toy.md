todays patient is this:


![[pic1_toycam.jpg]]

a toy camera with "decent" resolution and display. it has usb port, a micro SD card slot and a bunch of buttons. this  toy stopped charging and refuse to turn on. it happen when my friend tried to charge this camera using his powerbank. 

at a glance this toy case looks like welded by ultrasonics. smooth finish and no sign of screws. but after 2 hours of futile attemp to pry it open, i found out that the front "sticker" was hiding the screws.

![[pic2_cover.jpg]]

opening the screw, the back cover can be opened. and after removing the screen from its connector slot, we have the mainboard. 

![[pic3_mainboard.jpg]]

i begin to measure voltages in various point. notably the power supply and the battery. one thing i noticed, when plugging the usb cable, the light indicator started to blink dimly.

i checked the battery voltages and it got 0.4V!! so, i thought the low battery was the culprit. but after disconnecting the battery and measure it again, it has normal 3.7V!!

looks like we have a short circuit somewhere. so i busted out my (workshop)  thermal camera and start recording while its powered on. lo and behold, we have 2 heat spots!! one in a rectifier diode and one in an LDO chip.

![[pic4_ldo.jpg]]

the chip ia marked S10Bxxx and after finding the datasheet on google, i found out that this chip is a 1.5A constant current LDO. so replacing it with cheap LDO from some arduino board wont do. 

but before replacing it, lets test if this toy still works. after connecting the battery, hooking some wires with a 3.3v power supply, and plugging in the micro SD card, i was able to turn on this toy (phew).

![[pic5_psu3v3.jpg]]
![[pic6_stillon.jpg]]

whats left is to order some chips (under the name "1.2V CMOS IC") and wait for my friend to arrive with another botched toy cam (since got another one on home). i'll update later...

#repair #sjcam #funcam #S10B #instarepair