# ESPHome

## secrets.yaml

```code
# SSID & PASSWORD for local-wifi
# omjk
wifi_ssid_omjk: ""
wifi_password_omjk: ""

# sekt
wifi_ssid_sekt: ""
wifi_password_sekt: ""

# Secure Password Generator: https://passwordsgenerator.net/
# omjk
api_password_omjk: "F7SHdwmg36pGvKxc2juNnzPRU9BQ5ytZ"
ota_pass_omjk: "F7SHdwmg36pGvKxc2juNnzPRU9BQ5ytZ"
ap_password_omjk: "pjF79PSmRN6t5cL3"

# 32Byte Base64 String https://generate.plus/en/base64
api_key_omjk: "LTMfTQ2GwmBURmIWOL3Czw=="
```

## Leddriver

* Leddriver Files:
  * ESPHome files:
    * [leddriver-xx.yaml](./leddriver-xx.yaml)
  * Fritzing Files;
    * [PCB-LedDriver-V6.1.fzz](https://github.com/sekt1953/Fritzing/blob/main/My_PCB/LedDriver/v6.1/PCB-LedDriver-V6.1.fzz)
  * FreeCAD Files:
    * [LedDriverv6.1a.FCStd](https://github.com/sekt1953/FreeCAD/blob/main/LeadDriverv6.1/LedDriverv6.1a.FCStd)

### leddriver-xx.yaml

```code
substitutions:
# PCB LedDriver with optocoupler v6.1
  esphome_name: "leddriver-xx"

  id_hub0: "pcf8574_hub0"
  id_hub1: "pcf8574_hub1"
  id_hub2: "pcf8574_hub2"
  id_hub3: "pcf8574_hub3"
  id_hub4: "pcf8574_hub4"
  id_hub5: "pcf8574_hub5"
  id_hub6: "pcf8574_hub6"
  id_hub7: "pcf8574_hub7"

# PCF8574P & PCF8575
# 8bit portudvidelse I2C (2 wire) interface DIL16 Adresserbar til 
# hex:  0x20 0x21 0x22 0x23 0x24 0x25 0x26 0x27

  addr_hub0: "0x20"
  addr_hub1: "0x21"
  addr_hub2: "0x22"
  addr_hub3: "0x23"
  addr_hub4: "0x24"
  addr_hub5: "0x25"
  addr_hub6: "0x26"
  addr_hub7: "0x27"

# PCF8574AP
# 8bit portudvidelse I2C (2 wire) interface DIL16 Adresserbar til 
# hex: 0x38 0x39 0x3a 0x3b 0x3c 0x3d 0x3e 0x3f   

#  addr_hub0: "0x38"
#  addr_hub1: "0x39"
#  addr_hub2: "0x3a"
#  addr_hub3: "0x3b"
#  addr_hub4: "0x3c"
#  addr_hub5: "0x3d"
#  addr_hub6: "0x3e"
#  addr_hub7: "0x3f"

  i2c_sda: "21"
  i2c_scl: "22"
  i2c_scan: "true"
  i2c_id: "bus_a"

  track_delayed_off: 1000ms

esphome:
  name: ${esphome_name}
  friendly_name: ${esphome_name}

esp32:
  board: esp32dev
  framework:
    type: arduino

# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: !secret api_key_omjk

ota:
  password: !secret ota_pass_omjk
wifi:
  networks:
  - ssid: !secret wifi_ssid_omjk
    password: !secret wifi_password_omjk
  - ssid: !secret wifi_ssid_sekt
    password: !secret wifi_password_sekt
  - ssid: !secret wifi_ssid_finn
    password: !secret wifi_password_finn

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "${esphome_name} Fallback Hotspot"
    password: !secret ap_password_omjk

captive_portal:

text_sensor:
  - platform: wifi_info
    ip_address:
      name: "IP Address ${esphome_name}"
    ssid:
      name: "Connected SSID ${esphome_name}"
    bssid:
      name: "Connected BSSID ${esphome_name}"
    mac_address:
      name: "Mac Wifi Address ${esphome_name}"

button:
  - platform: restart
    name: "Restart ${esphome_name}"

i2c:
  sda: ${i2c_sda}
  scl: ${i2c_scl}
  scan: ${i2c_scan}  
  id: ${i2c_id}

# pcf8574P
# 8bit portudvidelse I2C (2 wire) interface DIL16 Adresserbar til 
# hex:  0x20 0x21 0x22 0x23 0x24  0x25 0x26 0x27

# pcf8574AP
# 8bit portudvidelse I2C (2 wire) interface DIL16 Adresserbar til 
# hex: 0x38 0x39 0x3a 0x3b 0x3c 0x3d 0x3e 0x3f   

pcf8574:
  - id: ${id_hub0}  
    address: ${addr_hub0}
    pcf8575: false
  - id: ${id_hub1} 
    address: ${addr_hub1}
    pcf8575: false
  - id: ${id_hub2}
    address: ${addr_hub2}
    pcf8575: false
  - id: ${id_hub3}
    address: ${addr_hub3}
    pcf8575: false
  - id: ${id_hub4}
    address: ${addr_hub4}
    pcf8575: false
  - id: ${id_hub5}
    address: ${addr_hub5}
    pcf8575: false
  - id: ${id_hub6}
    address: ${addr_hub6}
    pcf8575: false
  - id: ${id_hub7}
    address: ${addr_hub7}
    pcf8575: false

# LedDriver v6.1
# Individual input hub0
switch:
  - platform: gpio
    name: "_00"
    pin:
      pcf8574: ${id_hub0}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_01"
    pin:
      pcf8574: ${id_hub0}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_02"
    pin:
      pcf8574: ${id_hub0}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_03"
    pin:
      pcf8574: ${id_hub0}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_04"
    pin:
      pcf8574: ${id_hub0}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_05"
    pin:
      pcf8574: ${id_hub0}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_06"
    pin:
      pcf8574: ${id_hub0}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_07"
    pin:
      pcf8574: ${id_hub0}
      number: 7
      mode:
        output: true
      inverted: true
      
# Individual input hub1
#switch:
  - platform: gpio
    name: "_10"
    pin:
      pcf8574: ${id_hub1}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_11"
    pin:
      pcf8574: ${id_hub1}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_12"
    pin:
      pcf8574: ${id_hub1}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_13"
    pin:
      pcf8574: ${id_hub1}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_14"
    pin:
      pcf8574: ${id_hub1}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_15"
    pin:
      pcf8574: ${id_hub1}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_16"
    pin:
      pcf8574: ${id_hub1}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_17"
    pin:
      pcf8574: ${id_hub1}
      number: 7
      mode:
        output: true
      inverted: true
      
# Individual input hub2
#switch:
  - platform: gpio
    name: "_20"
    pin:
      pcf8574: ${id_hub2}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_21"
    pin:
      pcf8574: ${id_hub2}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_22"
    pin:
      pcf8574: ${id_hub2}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_23"
    pin:
      pcf8574: ${id_hub2}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_24"
    pin:
      pcf8574: ${id_hub2}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_25"
    pin:
      pcf8574: ${id_hub2}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_26"
    pin:
      pcf8574: ${id_hub2}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_27"
    pin:
      pcf8574: ${id_hub2}
      number: 7
      mode:
        output: true
      inverted: true

# Individual input hub3
#switch:
  - platform: gpio
    name: "_30"
    pin:
      pcf8574: ${id_hub3}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_31"
    pin:
      pcf8574: ${id_hub3}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_32"
    pin:
      pcf8574: ${id_hub3}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_33"
    pin:
      pcf8574: ${id_hub3}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_34"
    pin:
      pcf8574: ${id_hub3}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_35"
    pin:
      pcf8574: ${id_hub3}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_36"
    pin:
      pcf8574: ${id_hub3}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_37"
    pin:
      pcf8574: ${id_hub3}
      number: 7
      mode:
        output: true
      inverted: true

# Individual input hub4
#switch:
  - platform: gpio
    name: "_40"
    pin:
      pcf8574: ${id_hub4}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_41"
    pin:
      pcf8574: ${id_hub4}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_42"
    pin:
      pcf8574: ${id_hub4}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_43"
    pin:
      pcf8574: ${id_hub4}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_44"
    pin:
      pcf8574: ${id_hub4}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_45"
    pin:
      pcf8574: ${id_hub4}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_46"
    pin:
      pcf8574: ${id_hub4}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_47"
    pin:
      pcf8574: ${id_hub4}
      number: 7
      mode:
        output: true
      inverted: true

# Individual input hub5
#switch:
  - platform: gpio
    name: "_50"
    pin:
      pcf8574: ${id_hub5}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_51"
    pin:
      pcf8574: ${id_hub5}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_52"
    pin:
      pcf8574: ${id_hub5}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_53"
    pin:
      pcf8574: ${id_hub5}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_54"
    pin:
      pcf8574: ${id_hub5}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_55"
    pin:
      pcf8574: ${id_hub5}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_56"
    pin:
      pcf8574: ${id_hub5}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_57"
    pin:
      pcf8574: ${id_hub5}
      number: 7
      mode:
        output: true
      inverted: true

# Individual input hub6
#switch:
  - platform: gpio
    name: "_60"
    pin:
      pcf8574: ${id_hub6}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_61"
    pin:
      pcf8574: ${id_hub6}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_62"
    pin:
      pcf8574: ${id_hub6}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_63"
    pin:
      pcf8574: ${id_hub6}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_64"
    pin:
      pcf8574: ${id_hub6}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_65"
    pin:
      pcf8574: ${id_hub6}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_66"
    pin:
      pcf8574: ${id_hub6}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_67"
    pin:
      pcf8574: ${id_hub6}
      number: 7
      mode:
        output: true
      inverted: true

# Individual input hub7
#switch:
  - platform: gpio
    name: "_70"
    pin:
      pcf8574: ${id_hub7}
      number: 0
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_71"
    pin:
      pcf8574: ${id_hub7}
      number: 1
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_72"
    pin:
      pcf8574: ${id_hub7}
      number: 2
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_73"
    pin:
      pcf8574: ${id_hub7}
      number: 3
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_74"
    pin:
      pcf8574: ${id_hub7}
      number: 4
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_75"
    pin:
      pcf8574: ${id_hub7}
      number: 5
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_76"
    pin:
      pcf8574: ${id_hub7}
      number: 6
      mode:
        output: true
      inverted: true
  - platform: gpio
    name: "_77"
    pin:
      pcf8574: ${id_hub7}
      number: 7
      mode:
        output: true
      inverted: true
```
