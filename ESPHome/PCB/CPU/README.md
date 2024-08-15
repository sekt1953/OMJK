# Cpu

## [Olimex ESP32-POE-ISO-16MB](https://www.olimex.com/Products/IoT/ESP32/ESP32-POE-ISO/open-source-hardware)

|ESP32-POE-ISO-GPIO|
|:---:|
|![schem](./Olimex_ESP32-POE-ISO/ESP32-POE-ISO-GPIO.png)|

|ESP32-POE-ISO-revision-J-dimensions|
|:---:|
|![schem](./Olimex_ESP32-POE-ISO/Skærmbillede%20fra%202024-08-15%2021-12-50.png)|

## Prototype

### ESP32-Dev 30Pin med I2C Interface

|Schematic|
|:---:|
|![schem](./ESP32_30Pin_I2C_Board_a/ESP32_30Pin_I2C_Board_a_schem.png)|

|Breadboard|
|:---:|
|![Breadboard](./ESP32_30Pin_I2C_Board_a/ESP32_30Pin_I2C_Board_a_bb.png)|

* Fritzing files:
  * [ESP32_30Pin_I2C_Board_a.fzz](./ESP32_30Pin_I2C_Board_a/ESP32_30Pin_I2C_Board_a.fzz)

#### Forskellige måder at bruge dette print på

* Version 1 - 5V forsyning:
  * Tilslut 5V til J4
  * Forbind I2C interface via J1
  * NB! Der må ikke tilsluttes 3V3 til J5
* Version 2 - 3V3 forsyning:
  * Tilslut 3V3 til J5
  * Forbind I2C interface via J1
  * NB! Der må ikke tilsluttes 5V til J1
  * Denne løsning bruges lige nu sammen med [SporskifterDriver Printet](../SporskifteDriver/README.md).

#### Montage plade for ESP32-Dev 30Pin med I2C Interface og 5V Mini DC-DC Converter

|Esp32-MiniPow_Dev|Esp32-Dev|
|:---:|:---:|
|![Esp32-MiniPow_Dev](./ESP32_30Pin_I2C_Board_a/FreeCAD-Files/Esp32-MiniPow_Dev-Body.png)|![](./ESP32_30Pin_I2C_Board_a/FreeCAD-Files/Skærmbillede%20fra%202024-07-08%2016-51-11.png)

* FreeCAD files:
  * [Esp32-MiniPow_Dev.FCStd](./ESP32_30Pin_I2C_Board_a/FreeCAD-Files/Esp32-MiniPow_Dev.FCStd)
  * [Esp32-MiniPow_Dev-Body.3mf](./ESP32_30Pin_I2C_Board_a/FreeCAD-Files/Esp32-MiniPow_Dev-Body.3mf)
  * [Esp32-Dev.FCStd](./ESP32_30Pin_I2C_Board_a/FreeCAD-Files/Esp32-Dev.FCStd)
  * [Esp32-Dev-Body.3mf](./ESP32_30Pin_I2C_Board_a/FreeCAD-Files/Esp32-Dev-Body.3mf)
