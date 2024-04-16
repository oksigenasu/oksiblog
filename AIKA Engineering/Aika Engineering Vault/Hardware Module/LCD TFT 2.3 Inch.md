# 3.2inch SPI Module MSP3218

![[LCD TFT 2.3 Inch img1.png]]

Spesifikasi :
- 3.2-inch color screen
- Support 65K color display
- 320X240 resolution
- Optional touch function
- Easy to expand the experiment with SD card slot
- Using the SPI serial bus
- Driver IC ILI9341
- Module Size 55.04x89.3 (mm)

Pinout :
![[LCD TFT 2.3 Inch img2.png]]

| Pin Label | Description |
|  ---- |----|
| VCC | 5V/3V3 Power Input |
| GND | Ground |
| CS | LCD chip select signal, low level enable |
| RESET | LCD reset signal, low level reset |
| DC/RS | LCD register / data selection signal, high level: register, low level: data |
| SDI(MOSI) | SPI bus write data signal |
| SCK | SPI bus clock signal |
| LED | Backlight control, high level lighting, if not controlled, connect 3.3V always bright |
| SDO(MISO) | SPI bus read data signal, if you do not need to the read function, you can not connect it |
| T_CLK | Touch SPI bus clock signal |
| T_CS | Touch screen chip select signal, low level enable |
| T_DIN | Touch SPI bus input |
| T_DO | Touch SPI bus output |
| T_IRQ | Touch screen interrupt signal, low level when touch is detected |

Library Support Tested:
- https://github.com/Bodmer/TFT_eSPI

Project :
1. Fire Alarm Asahimas
	- https://github.com/aikaglobal/Fire_Alarm

Note :
1. fixing TFT lcd white blank after change computer / update library
	- open User_Setup_Select.h from .pio\libdeps\TFT_eSPI\
	- uncomment line 79 #include <User_Setups/Setup42_ILI9341_ESP32.h> and save file
	- open file from .pio\libdeps\TFT_eSPI\User_Setups/Setup42_ILI9341_ESP32.h
	- change defined TFT_CS, TFT_DC, and TFT_RST according to schematics (27, 32, and 25) and save
	- do this whenever first install/update library