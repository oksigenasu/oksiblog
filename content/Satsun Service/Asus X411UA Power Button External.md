---
title: Asus X411UA Power Button External
draft: false
tags:
  - keyboard
  - laptop
  - repair
cssclasses: 
aliases: 
date: 2022-12-04
---
Yesterday patients are these pair of Asus X411UA with broken keyboard.  
the user want to use it as a server since it got good specs and basically free (the user got it from decommisioned government property), thats why they wanted to add an on off switch.  
  
the problem with this model is, the power switch is in a row with the keyboard (and also, the keyboard build quality sucks) so adding a new power switch requires wiring the power switch signal on the keyboard connector port to an external button.  
  
based on experience, wiring a cable on a tight spot connector was a hassle. so i turn to the schematic and found an unused pad under the nvme ssd that connected to power switch signal (PWR_SW#). since this signal is active low, i just need to connect this signal to ground to switch on the thing.  
  
another thing the user wants is to enable the power light once the power switch is pressed. since they provided with a led enabled button, i just need to find power led signal from the schematic and wiring it to the led. 

from the schematic, i found the traces from the signal (PWR_LED) led to a pad under the board and a transistor on top of keyboard connector. to make sure the signal works properly, i check the voltage on the traces when the computer is on and off. the result are 3.2V and 0V respectively, enough to power the led on the button (i also make sure the led on the button can handle 3.3V).  
  
with all the traces found, all i need to do is solder the wires, test, and... done.