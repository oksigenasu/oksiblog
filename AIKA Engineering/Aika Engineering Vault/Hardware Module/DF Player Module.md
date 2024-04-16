# DF Player MH2024K-16SS
![[DF Player Module img1.png]]

Spesifikasi :
- Sampling rates (kHz): 8/11.025/12/16/22.05/24/32/44.1/48
- 24 -bit DAC output, support for dynamic range 90dB , SNR support 85dB
- Fully supports FAT16 , FAT32 file system, maximum support 32G of the TF card, support 32G of U disk, 64M bytes NORFLASH
- A variety of control modes, I/O control mode, serial mode, AD button control mode
- advertising sound waiting function, the music can be suspended. when advertising is over in the music continue to play
- audio data sorted by folder, supports up to 100 folders, every folder can hold up to 255 songs
- 30 level adjustable volume, 6 -level EQ adjustable
- Supply Voltage: 5VDC
- Chip MH2024K-16SS

Pinout :
![[DF Player Module img2.png]]

Library Support Tested:
- https://github.com/DFRobot/DFRobotDFPlayerMini

Project :
1. JWS IQOMA
	- https://github.com/aikaglobal/JWS_V5_WIFI
	- https://github.com/aikaglobal/JWS_V5_GPS

Note :
1. Terdapat 2 jenis Chip (MH2024K-16SS & MH2024K-24SS)
	- MH2024K-16SS -> IC 16 PIN
	- MH2024K-24SS -> IC 24 PIN (Beberapa fungsi pada library tidak mendukung)