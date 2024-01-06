# Lovelace

## Views

### Home

![Home](./images/Skærmbillede%20fra%202024-01-03%2021-52-45.png)

```code
type: vertical-stack
cards:
  - type: horizontal-stack
    cards:
      - type: entities
        entities:
          - person.omjk
  - type: horizontal-stack
    cards:
      - type: button
        show_name: true
        show_icon: true
        tap_action:
          action: call-service
          service: hassio.host_shutdown
          target: {}
        icon: mdi:power-plug-off
        entity: ''
      - type: button
        show_name: true
        show_icon: true
        tap_action:
          action: call-service
          service: hassio.host_reboot
          target: {}
        icon: mdi:restart
        entity: ''
```

### LedDriver

![LedDriver-00-xx](./images/Skærmbillede%20fra%202024-01-06%2012-04-10.png)

```code
type: entities
entities:
  - entity: switch.leddriver_00_00
    name: _00
  - entity: switch.leddriver_00_01
    name: _01
  - entity: switch.leddriver_00_02
    name: _02
  - entity: switch.leddriver_00_03
    name: _03
  - entity: switch.leddriver_00_04
    name: _04
  - entity: switch.leddriver_00_05
    name: _05
  - entity: switch.leddriver_00_06
    name: _06
  - entity: switch.leddriver_00_07
    name: _07
title: leddriver-00-0x
state_color: true
show_header_toggle: true
```

```code
type: entities
entities:
  - entity: switch.leddriver_00_10
    name: _10
  - entity: switch.leddriver_00_11
    name: _11
  - entity: switch.leddriver_00_12
    name: _12
  - entity: switch.leddriver_00_13
    name: _13
  - entity: switch.leddriver_00_14
    name: _14
  - entity: switch.leddriver_00_15
    name: _15
  - entity: switch.leddriver_00_16
    name: _16
  - entity: switch.leddriver_00_17
    name: _17
title: leddriver-00-1x
state_color: true
show_header_toggle: true
```

![LedDriver-00](./images/Skærmbillede%20fra%202024-01-06%2012-10-11.png)

```code
type: entities
entities:
  - entity: update.leddriver_00_firmware
    name: Firmware
  - entity: button.leddriver_00_restart_leddriver_00_3
    name: Restart leddriver-00
  - entity: sensor.leddriver_00_connected_bssid_leddriver_00_3
    name: Connected BSSID leddriver-00
  - entity: sensor.leddriver_00_connected_ssid_leddriver_00_3
    name: Connected SSID leddriver-00
  - entity: sensor.leddriver_00_ip_address_leddriver_00_3
    name: IP Address leddriver-00
  - entity: sensor.leddriver_00_mac_wifi_address_leddriver_00_3
    name: Mac Wifi Address leddriver-00
title: leddriver-00
```