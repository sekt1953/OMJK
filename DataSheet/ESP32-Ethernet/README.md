# ESP32 Ethernet

## Kilder

* DroneBot Workshop
  * [Wired networking, PoE, and a self-powered web camera](https://dronebotworkshop.com/esp32-ethernet/)
* [ardustore.dk/](https://ardustore.dk/)
  * [Seeeduino XIAO ESP32-S3 Udviklingsboard](https://ardustore.dk/produkt/seeeduino-xiao-esp32-s3-udviklingsboard)
  * [USR-ES1 W5500 Ethernet Module](https://ardustore.dk/produkt/usr-es1-w5500-ethernet-module)
  * [ESP32-WROOM WT32-ETH01 Udviklingsboard](https://ardustore.dk/produkt/esp32-wroom-wt32-eth01-udviklingsboard)
  * [ESP32-C3 WT32-ETH01-EVO PoE](https://ardustore.dk/produkt/esp32-c3-wt32-eth01-poe-udviklingsboard)
* Waveshare
  * [ESP32 Basic Tutorials](https://docs.waveshare.com/ESP32-Tutorials-Intro)
  * [Waveshare ESP32-S3-ETH](https://www.waveshare.com/esp32-s3-eth.htm?srsltid=AfmBOoquH_gwIqmhh33OhDhZphzOZIgQlENh6ChBgzdErHBRXzQI3UgG)
* Olimex
  * [Olimex ESP32-P4-ETH](https://www.olimex.com/Products/IoT/ESP32-P4/ESP32-P4-DevKit/open-source-hardware)
  
## AI-genereret Config files

* [Waveshare ESP32-S3-ETH](https://www.waveshare.com/esp32-s3-eth.htm?srsltid=AfmBOoquH_gwIqmhh33OhDhZphzOZIgQlENh6ChBgzdErHBRXzQI3UgG)
  * [waveshare-esp32-s3-eth.yaml](../../ESPHome/AI-Input/waveshare-esp32-s3-eth.yaml)
  * Key Setup Details
    * First Install: Connect the board to your computer via the onboard USB-C port to perform the initial compilation and USB flash.
    * Network: Subsequent updates can be done over-the-air (OTA) via your wired Ethernet connection.
    * Wi-Fi: Wi-Fi is disabled by default in this configuration to force hardwired Ethernet operation.
    * If you plan to attach peripherals like the OV2640/OV5640 camera, an SD card, or industrial relays/inputs, tell me which expansions you are using so I can add them to your configuration file.
* [Olimex ESP32-P4-ETH](https://www.olimex.com/Products/IoT/ESP32-P4/ESP32-P4-DevKit/open-source-hardware)
  * [Olimex_ESP32-P4-DevKit.yaml](../../ESPHome/AI-Input/Olimex_ESP32-P4-DevKit.yaml)
  * Essential Setup Notes
    * Framework Constraint: The ESP32-P4 architecture requires the esp-idf framework. The legacy Arduino framework is not supported for this chip.
    * Connectivity: The core ESP32-P4 chip does not have onboard Wi-Fi or Bluetooth. Wireless features require an attached companion module (such as an ESP32-C6 via esp32_hosted) or connection via the board's hardwired Ethernet port.
    * First Flash: Connect the board to your computer via the USB Type-C port (using native USB/JTAG) for the initial compilation and upload.
    * If you are attaching a specific wireless co-processor module or a MIPI display/camera peripheral, tell me the exact model and I will add those sections to your YAML.  
