# Module ESP-WROOM-32
![[ESP32 img1.png]]

Spesifikasi :
- Xtensa® Dual-Core 32-bit LX6 microprocessors, up to 600 DMIPS
- 448 KByte ROM
- 520 KByte SRAM
- 16 KByte SRAM in RTC
- QSPI Flash/SRAM, up to 4 x 16 MBytes
- Power supply: 2.2 V to 3.6 V
- 18 Analog-to-Digital Converter (ADC) channels
- 3 SPI interfaces
- 3 UART interfaces
- 2 I2C interfaces
- 16 PWM output channels
- 2 Digital-to-Analog Converters (DAC)
- 2 I2S interfaces
- 10 Capacitive sensing GPIOs
- Package size: 18mm x 25mm x 3mm

Pinout :
![[ESP32 img2.png]]

| GPIO | Input | Output | Notes |
|  ---- |----|  ---- |----|
| 0 | PULLUP | OK | outputs PWM signal at boot, must be LOW to enter flashing mode |
| 1 | TX pin | OK | debug output at boot |
| 2 | OK | OK | connected to on-board LED, must be left floating or LOW to enter flashing mode |
| 3 | OK | RX pin | HIGH at boot |
| 4 | OK | OK |  |
| 5 | OK | OK | outputs PWM signal at boot, strapping pin |
| 6 | X | X | connected to the integrated SPI flash |
| 7 | X | X | connected to the integrated SPI flash |
| 8 | X | X | connected to the integrated SPI flash |
| 9 | X | X | connected to the integrated SPI flash |
| 10 | X | X | connected to the integrated SPI flash |
| 11 | X | X | connected to the integrated SPI flash |
| 12 | OK | OK | boot fails if pulled high, strapping pin |
| 13 | OK | OK |  |
| 14 | OK | OK | outputs PWM signal at boot |
| 15 | OK | OK | outputs PWM signal at boot, strapping pin |
| 16 | OK | OK |  |
| 17 | OK | OK |  |
| 18 | OK | OK |  |
| 19 | OK | OK |  |
| 21 | OK | OK |  |
| 22 | OK | OK |  |
| 23 | OK | OK |  |
| 25 | OK | OK |  |
| 26 | OK | OK |  |
| 27 | OK | OK |  |
| 32 | OK | OK |  |
| 33 | OK | OK |  |
| 34 | OK | - | input only |
| 35 | OK | - | input only |
| 36 | OK | - | input only |
| 39 | OK | - | input only |


Project :
1. JWS IQOMA versi kecil
	- https://github.com/aikaglobal/JWS_V5_WIFI
	- https://github.com/aikaglobal/JWS_V5_GPS
	- https://github.com/aikaglobal/NTPC_MATRIX_P3_ESP32