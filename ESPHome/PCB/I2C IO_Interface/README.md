# I2C IO_Interface

## MCP23017

|Fritzing Schematic|
|:---|
|![schem](./mcp23017/mcp23017_300_schem.png)|
|Fritzing PCB|
|![PCB](./mcp23017/mcp23017_300_pcb.png)|
|MCP23017 PinOut|
|![schem](./mcp23017/MCP23017.png)|

* Fritzing files:
  * [I2C_IO_Interface.fzz](./mcp23017/mcp23017_300.fzz)
* ESPHome
  * [MCP23017 Component](https://esphome.io/components/mcp230xx#mcp23017-label)
  * [Microchip MCP23017 Datasheet](https://ww1.microchip.com/downloads/en/devicedoc/20001952c.pdf)

## I2C_IO_Interface OLD Version with PCF8574

|Fritzing Schematic|
|:---:|
|![schem](./PCF8574/I2C_IO_Interface_schem.png)|
|Fritzing PCB|
|![PCB](./PCF8574/I2C_IO_Interface_pcb.png)|
|FreeCAD|
|![FreeCAD](./PCF8574/FreeCAD_Files/Skærmbillede%20fra%202024-07-06%2017-55-29.png)|
|PCF8574 PinOut|
|![schem](./PCF8574/Skærmbillede%20fra%202024-08-15%2021-27-31.png)|

* Fritzing files:
  * [I2C_IO_Interface.fzz](./PCF8574/I2C_IO_Interface.fzz)
  * [bom](./PCF8574/I2C_IO_Interface_bom.html)
  * [svg files](./PCF8574/svg_I2C_IO_Interface/)
* FreeCAD Files:
  * [I2C_IO_Interface_v3.FCStd](./PCF8574/FreeCAD_Files/I2C_IO_Interface_v3.FCStd)
  * [I2C_IO_Interface_v3-Body.3mf](./PCF8574/FreeCAD_Files/I2C_IO_Interface_v3-Body.3mf)
* ESPHome
  * [PCF8574 I/O Expander](https://esphome.io/components/pcf8574)
  * [Texas PCF8574 DataSheet](https://www.ti.com/lit/ds/symlink/pcf8574.pdf)

## Forskellige måder jeg bruger dette print på

* For alle versioner gælder:
  * De forbindes til [ESP32 ESP32S 30Pin Expansion board](../CPU/README.md) I2C konector for data og power, der kan max tilsluttes to 2 af disse kort til I2C interface.
  * Kabel ser her: 
    * [mcu-connector-til-i2c-io_interface](../../Includes/0_Default_files/I2C_Kabler/I2C-Kabel.md#mcu-connector-til-i2c-io_interface)
* Version 1 - General Input:
  * Bruges som input kort for trykknapper og tilbage melding fra sporskifte motorer
  * Monteret med 4 stk. 9 polet skrue terminaler type KF128 2.54mm og pullup modstande på 2K2 ohm.
  * Default include files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_input.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_input.yaml)
  * Se eksample her i Hjulby-Pult-Led-01:
    * [ju-pl-01.yaml](../../ju-pl-01.yaml)
* Version 2 - Block-Detection med BD20:
  * Bruges som input kort for [Block-Detection med BD20](../BlockDetection/BD20/NCE_BD20.png), sammen med ULN2803 input interface kort:
  * Monteret med 40 PIN Single Row Right Angle FEMALE PIN HEADER 2.54MM og pullup modstande på 2K2 ohm.
  * Default include files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_input.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_input.yaml)
  * Se eksample her i Hjulby-Block-Detection-00
    * [ju-bd-00.yaml](../../ju-bd-00.yaml)
* Version 3 - SporskifteDriver:
  * Bruges som output kort, sammen med SporskifteDriver kortet
  * Monteret med 4 stk. 9 polet skrue terminaler type KF128 2.54mm, men uden pullup modstande, da TB6612FNG har indbygget pulldown modstande.
  * Default include files for ESP32:
    * [.pcf8574_ids.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_ids.yaml)
    * [.pcf8574_output.yaml](../../Includes/0_Default_files/PCF8574/.pcf8574_output.yaml)
  * Se eksample her i Hjulby-Sporskifte-00
    * [ju-sp-00.yaml](../../ju-sp-00.yaml)
