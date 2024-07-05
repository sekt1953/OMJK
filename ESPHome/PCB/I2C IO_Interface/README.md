# I2C IO_Interface

|Schematic / PCB|
|:---:|
|![schem](./I2C_IO_Interface_schem.png)|
|![PCB](./I2C_IO_Interface_pcb.png)|

* Fritzing files:
  * [I2C_IO_Interface.fzz](./I2C_IO_Interface.fzz)
  * [bom](./I2C_IO_Interface_bom.html)
  * [svg files](./svg_I2C_IO_Interface/)

## Forskellige måder at bruge dette print

* Version 1 - General Input:
  * Bruges som input kort for trykknapper og tilbage melding fra sporskifte motorer
  * Monteret med 4 stk. 9 polet skrue terminaler type KF128 2.54mm og pullup modstande på 2K2 ohm.
  * Default files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_input.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_input.yaml)
* Version 2 - Block-Detection:
  * Bruges som input kort for Block-Detection med BD20, sasmmen med ULN2803 interface kort:
  * Monteret med 40 PIN Single Row Right Angle FEMALE PIN HEADER 2.54MM og pullup modstande på 2K2 ohm.
  * Default files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_input.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_input.yaml)
* Version 3 - SporskifteDriver:
  * Bruges som output kort, sammen med SporskifteDriver kortet
  * Monteret med 4 stk. 9 polet skrue terminaler type KF128 2.54mm, men uden pullup modstande, da TB6612FNG har indbygget pulldown modstande.
  * Default files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_output.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_output.yaml)

