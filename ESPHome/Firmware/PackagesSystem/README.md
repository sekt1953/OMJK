# ESPHome Packages

## Sources

* Youtube
  * [Home Automator](https://www.youtube.com/@homeautomatorza)
    * [ESPHome Coding practices, tips and tricks, Tutorial 1, Foundation Part 2](https://youtu.be/G9WRg6jk7xk)
    * [ESPHome Coding Practices, Tips and Tricks - Tutorial 2 - Standard Board Configurations](https://youtu.be/___CvvfPEt4)
    * [ESPHome Coding Practices, Tips and Tricks - Tutorial 3 - Our First Device](https://youtu.be/eyEGK1eKyDM)
    * [ESPHome Web Server and Web Server Updates in ESPHome 2024.10](https://youtu.be/7xuKtR4a6c4)
    * GitHub Repositorie
      * [Code from the Home Automator YouTube Channel](https://github.com/homeautomatorza/esphome/tree/main)
      * [ESPHome Modules](https://github.com/homeautomatorza/ESPHome-Modules/tree/main)
* ESPHome.io
  * [Packages](https://esphome.io/components/packages/)
  * [Substitutions](https://esphome.io/components/substitutions/)
* AI
  * [The Substitution Default Overriding Pattern](../../AI-Input/The%20Substitution%20Default%20Overriding%20Pattern.md)

## Substitutions

### What do AI say about "The Substitution Default Overriding Pattern"

* ESPHome does not support native if statements:
  * ESPHome does not support native if statements or conditional logic inside a YAML !include statement. Because YAML is purely a static descriptive language and lacks a built-in preprocessor engine,
  * ***you cannot write an expression like !include ${ 'wifi.yaml' if status else 'ethernet.yaml' }***
* Strategy 1: The Substitution Default Overriding Pattern
  * Instead of choosing which file to include, include a template file that relies on ESPHome Substitutions. You can define blank or default behaviors that you override only when needed.
  * common_wifi.yaml (The Included File):

```yaml  
wifi:
  ssid: "MyHomeWiFi"
  password: "SecretPassword"
  # If $fast_connect is text-replaced with 'fast_connect: true', it enables it.
  # If left as an empty comment placeholder, it does nothing.
  $fast_connect_setting 
```

*
  * device.yaml (Your Main File):

```yaml  
substitutions:
  # Overrides the blank placeholder with valid YAML config
  fast_connect_setting: "fast_connect: true" 

<<: !include common_wifi.yaml
```

### My Substitution Variables for Wavwshare ESP32-S3 ETH

```yaml
substitutions:
# ...
# W5500 Lan with RST Pin.
  w5500_mosi: GPIO11
  w5500_miso: GPIO12
  w5500_clk:  GPIO13
  w5500_cs: GPIO14
  w5500_int: GPIO10
  w5500_rst: GPIO9
```

#Lan Package for Olimex-ESP32-P4-Devkit
ethernet:
  type: IP101
  mdc_pin: GPIO31
  mdio_pin: GPIO52
  clk:
    pin: GPIO50
    mode: CLK_EXT_IN
  phy_addr: 1
  power_pin: GPIO51
  
#Lan Package for Wavwshare ESP32-S3 ETH
  ethernet:
  type: W5500
  clk_pin: GPIO13
  mosi_pin: GPIO11
  miso_pin: GPIO12
  cs_pin: GPIO14
  interrupt_pin: GPIO10
  reset_pin: GPIO9