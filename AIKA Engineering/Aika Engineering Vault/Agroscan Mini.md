#project #agroobot #agrooscan #hardware #iot

## About
- 7 in 1 soil sensor interface for Agroosoil cloud service with build in GPS
- using TTGO T-Display
- gonna update later...

## How to setup TFT_eSPI
- Open folder .pio/libdeps/{esp32dev}/TFT_eSPI/
- Open file **User_Setup_Select.h**
- comment line **`#include <User_Setup.h>`**
- uncomment line **`#include <User_Setups/Setup25_TTGO_T_Display.h>`**
- rebuild.
> DO THIS EVERYTIME LIBRARY UPDATED!

## Hardware
- TTGO T-Display
- GPS U-Blox Neo 6/7 + Antenna
- RS485 to TTL Converter
- RS485 7 in 1 Soil Sensor
- 18650 Battery and casing
- 5V output regulator
- 22mm metal button color
- 7 pin SD20 male-female connector
- JST-SH 1mm 4 pin male-female
- JST-SH 1mm 3 pin male-female