# I2C IO_Interface

|Schematic / PCB|
|:---:|
|![schem](./I2C_IO_Interface_schem.png)|
|![PCB](./I2C_IO_Interface_pcb.png)|

* Fritzing files:
  * [I2C_IO_Interface.fzz](./I2C_IO_Interface.fzz)
  * [bom](./I2C_IO_Interface_bom.html)
  * [svg files](./svg_I2C_IO_Interface/)

## Forskellige måder jeg bruger dette print på

* For alle versioner gælder:
  * De forbindes til [ESP32 ESP32S 30Pin Expansion board](../CPU/README.md) I2C konector for data og power, der kan max tilsluttes to 2 af disse kort til I2C interface.
  * Kabel ser her: 
    * [mcu-connector-til-i2c-io_interface](../../Includes/0_Default_files/I2C_Kabler/I2C-Kabel.md#mcu-connector-til-i2c-io_interface)
* Version 1 - General Input:
  * Bruges som input kort for trykknapper og tilbage melding fra sporskifte motorer
  * Monteret med 4 stk. 9 polet skrue terminaler type KF128 2.54mm og pullup modstande på 2K2 ohm.
  * Default files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_input.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_input.yaml)
  * Se eksample her i Hjulby-Pult-Led-01:
    * [ju-pl-01.yaml](../../ju-pl-01.yaml)
* Version 2 - Block-Detection:
  * Bruges som input kort for Block-Detection med BD20, sasmmen med ULN2803 interface kort:
  * Monteret med 40 PIN Single Row Right Angle FEMALE PIN HEADER 2.54MM og pullup modstande på 2K2 ohm.
  * Default files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_input.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_input.yaml)
  * Se eksample her i Hjulby-Block-Detection-00
    * [ju-bd-00.yaml](../../ju-bd-00.yaml)
* Version 3 - SporskifteDriver:
  * Bruges som output kort, sammen med SporskifteDriver kortet
  * Monteret med 4 stk. 9 polet skrue terminaler type KF128 2.54mm, men uden pullup modstande, da TB6612FNG har indbygget pulldown modstande.
  * Default files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_output.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_output.yaml)
  * Se eksample her i Hjulby-Sporskifte-00
    * [ju-sp-00.yaml](../../ju-sp-00.yaml)