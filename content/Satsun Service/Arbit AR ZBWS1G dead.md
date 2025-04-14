---
title: Arbit AR ZBWS1G dead
draft: false
tags:
  - repair
  - hardware
  - iot
cssclasses: 
aliases: 
date: 2024-02-25
---
Satsun service is back! (again)  
  
Today's patient is a Tuya 1 gang no neutral zigbee smart switch that identify as an ARBIT sponsored by [@thisislingga](https://www.instagram.com/thisislingga/)  
  
according to the donor, this smart switch has blown components inside. from the outside, we can see some burn marks on the corner.  
  
disassembling the switch, reveals the burnt component: a fuse. this means the component did its job well; when a short circuit occured, it sacrificed its body to take the brunt.  
  
the next step is to check if the low voltage circuit is still safe. looking at the silkscreen on the PCB, we can see VCC and GND on it. we can start to check from there.  
  
Using a continuity test, we check if there are any VCC that shorted to GND. Alhamdulillah, there are none, nada. so the low voltage circuit is safe (probably) .  
  
next, we try to turn on the low voltage circuit by injecting DC voltage to the VCC and GND using a power supply. for IoT devices like this, usually they used 3.3V or 5V for the supply voltage.  
  
setting the power supply to 3.3V and attaching the output to VCC and GND, we begin to inject the voltage. and lo and behold! the indicator light lightsup green! Nice!  
  
now, we just need to replace the fuse and this thing is good to go!  
  
or so i thought...

..after replacing the blown fuse with 1 Ohm resistor from leftover laptop charger, next step is to add a load to the switch and try to make it work. but before that, how does this switch operate without a neutral cable?  
  
looking at the wiring manual, we just need to plug the live wire (Hot) to the L terminal block and the load to the L1 terminal block. and we can control the load with the switch.  
  
still, how is the switch powering itself when the load is switched off!? using magic?  
  
a passive switch (like a "schakelaar" at our house) works by closing and opening electrical circuit around the load. when the circuit is open, the load won't get power. and when the circuit is closed, the load will turned on.  
  
with an electrically operated switch (relay), we have to supply a voltage to the switch. so a circuit must be closed around the relay for it to operate. but if the circuit is closed and always turned on, how to turn it off?  
  
turns out, this no-neutral switch thingy works by under-watt-ing the load when its time to shut it off, but still keep the watt high enough for the switch to operate [1].  
  
and when the load needs to be turned on, the switch will increase the wattage according to the load.  
  
by this configuration, the load will always in closed circuit but the energy that passed through is controlled by the switch.  
  
thats why on the specification, it shows:  
  
Output: 5~220W LED  
  
not 0~220W!! because the switch lowest wattage is 5W. so if we have a load that only need 5W to turn on, it will always turned on even if the switch are in off mode.  
  
okay, lets make a simple contraption to check the switch using a "stekker" and a "stopcontact". after wiring according to the manual, lets test the load and plug the stekker to an electric outlet.  
  
no sign of lights, but the load is turned on. wait, what!? how!? why!? something must be wrong....  

....after checking that the wire is good, and the wiring is according to the manual, what's left is to check the component on the PCB.  
  
there are a lot of component on the PCB and different component use different method to check (maybe another time).  
  
First culprit that found after checking the component is a shorted Triac T810-800B. this was found after realizing that the load and live terminal is shorted.  
  
removing this component eliminate the short on the load, but the indicator lights is still off. that means the AC to DC converter is not working.  
  
afer checking the diode one by one, turns out there was a diode that have 0.9V drop at reverse bias. removing this diode and re-checking the reverse bias shows that this diode is okay (because it shows OL after removing).  
  
this means something is leaking the voltage around the diode. checking the schematics confirm that the only thing that connected to the diode is an electrolyte capacitor (elco) that upon inspection, is sus.  
  
replacing the capacitor eliminates the leakage and for extra measure, the other elco is also replaced. now is the moment of truth!  
  
after preparing the contraption and triple check anything, this switch is ready for the debut! (apart from replacing the triac)  
  
carefully, the "stekker" is plugged into the power outlet. panic comes in a heartbeat when a couple of pop sound coming from the inside.  
  
...  
  
no light. lets try to press the switch. Alhamdulillah! the green light is on! and the load is active! wait, does this mean we dont need to replace the triac? huh...?  
  
whats left is to add the triac but since we dont use zigbee here that means this switch will only be a "fancy sakelaar".  
  
also, having to constantly under-watt-ing doesn't feel good for the load. maybe its okay for some load, but, better safe than sorry.  
  
whats next? maybe converting this into a wifi version? or add mechanic relay?