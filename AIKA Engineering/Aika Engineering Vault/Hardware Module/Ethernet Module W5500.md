
![[Ethernet Module W5500 img1.png]]

Spesifikasi :
- Power supply mode: 3.3V external power supply, current should be greater than 200mA
- Control interface form: 3.3 V TTL level, SPI interface; 2x single row pin
- PCB size (MM): 23 x 25 mm
- Dimensions (length x width x height): 28.5 x 23 x 24 mm
- 80 MHz high speed SPI interface
- Supports TCP, UDP, ICMP, IPv4, ARP, IGMP and PPPoE protocols
- Supports high-speed serial peripheral interface (SPI mode 0 ~ 3)

Pinout :
![[Ethernet Module W5500 img2.png]]

Library Support Tested:
- https://github.com/khoih-prog/Ethernet_Generic

Project :
1. NTCP
	- https://github.com/aikaglobal/NTPC_Eth_ENC
	- https://github.com/aikaglobal/NTPC_MK7_Eth
1. Fire Alarm Asahimas
	- https://github.com/aikaglobal/Fire_Alarm

Note :
1. PIN Reset tidak berfungsi
	- Solusi menggunakan Transistor sebagai Switch :
		![[Ethernet Module W5500 img3.png]]

2. Type seperti gambar dibawah, Pin Reset Berfungsi dengan baik
	![[Ethernet Module W5500 img4.png]]