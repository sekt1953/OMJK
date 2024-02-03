# Lovelace - Overview

* Overview - 'Raw configuration files'
  * [Raw configuration files:](./RawConfigurationFiles.yaml)

## Views as seen in 'Raw configuration editor'

```code
title: Hjem
views:
  - path: default_view
```

### Home

![Home](./images/Skærmbillede%20fra%202024-02-03%2009-36-05.png)

```code
type: vertical-stack
cards:
  - type: horizontal-stack
    cards:
      - type: entities
        entities:
          - person.omjk
        state_color: true
      - type: custom:simple-clock-card
        hide_seconds: null
        use_military: true
        font_size: 3rem
        paddingBottom_size: 25px
        paddingTop_size: 25px
  - type: horizontal-stack
    cards:
      - type: button
        tap_action:
          action: call-service
          service: hassio.host_shutdown
          target: {}
        icon: mdi:power-plug-off
        entity: ''
        show_state: true
        show_name: true
        show_icon: true
      - type: button
        tap_action:
          action: call-service
          service: hassio.host_reboot
          target: {}
        icon: mdi:restart
        entity: ''
        show_name: true
        show_icon: true
  - type: horizontal-stack
    cards:
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/leddriver
        icon: mdi:led-on
        entity: ''
        show_state: true
        name: LedDriver-00
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/leddriver-01
        icon: mdi:led-on
        entity: ''
        name: LedDriver-01
        show_state: false
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/leddriver-02
        icon: mdi:led-on
        entity: ''
        name: LedDriver-02
        show_state: false
  - type: horizontal-stack
    cards:
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/occupied-00
        icon: mdi:train
        name: Occupied-00
        hold_action:
          action: none
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/occupied-hp
        icon: mdi:train
        name: Occupied-Hp
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/occupied-00
        icon: ''
  - type: horizontal-stack
    cards:
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/reserved-00
        icon: mdi:fence
        name: Reserved
        hold_action:
          action: none
        show_state: false
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/occupied-00
        icon: ''
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: navigate
          navigation_path: /lovelace/occupied-00
        icon: ''
```

### PWM with pca9685

|||
|:---:|:---:|
|![pca9685-00-xx](./images/Skærmbillede%20fra%202024-01-22%2020-42-27.png)||

```code
type: vertical-stack
cards:
  - type: horizontal-stack
    cards:
      - type: light
        entity: light.pca9685_00_00
      - type: light
        entity: light.pca9685_00_01
      - type: light
        entity: light.pca9685_00_02
      - type: light
        entity: light.pca9685_00_03
  - type: horizontal-stack
    cards:
      - type: light
        entity: light.pca9685_00_04
      - type: light
        entity: light.pca9685_00_05
      - type: light
        entity: light.pca9685_00_06
      - type: light
        entity: light.pca9685_00_07
  - type: horizontal-stack
    cards:
      - type: light
        entity: light.pca9685_00_08
      - type: light
        entity: light.pca9685_00_09
      - type: light
        entity: light.pca9685_00_0a
      - type: light
        entity: light.pca9685_00_0b
  - type: horizontal-stack
    cards:
      - type: light
        entity: light.pca9685_00_0c
      - type: light
        entity: light.pca9685_00_color
      - type: light
        entity: light.pca9685_00_0e
      - type: light
        entity: light.pca9685_00_0f

```

```code
type: entities
entities:
  - entity: update.pca9685_00_firmware
    name: Firmware
  - entity: button.pca9685_00_restart_pca9685_00
    name: Restart pca9685-00
  - entity: sensor.pca9685_00_connected_bssid_pca9685_00
    name: Connected BSSID pca9685-00
  - entity: sensor.pca9685_00_connected_ssid_pca9685_00
    name: Connected SSID pca9685-00
  - entity: sensor.pca9685_00_ip_address_pca9685_00
    name: IP Address pca9685-00
  - entity: sensor.pca9685_00_mac_wifi_address_pca9685_00
    name: Mac Wifi Address pca9685-00
title: pca9685-00
```

### LedDriver

|||
|:---:|:---:|
|![LedDriver-00-xx](./images/Skærmbillede%20fra%202024-01-06%2012-04-10.png)|![LedDriver-00](./images/Skærmbillede%20fra%202024-01-06%2012-10-11.png)|

```code
  - title: LedDriver-00
    path: leddriver
    subview: true
    badges: []
    cards:
      - type: entities
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
      - type: entities
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
      - type: entities
        entities:
          - entity: switch.leddriver_00_20
            name: _20
          - entity: switch.leddriver_00_21
            name: _21
          - entity: switch.leddriver_00_22
            name: _22
          - entity: switch.leddriver_00_23
            name: _23
          - entity: switch.leddriver_00_24
            name: _24
          - entity: switch.leddriver_00_25
            name: _25
          - entity: switch.leddriver_00_26
            name: _26
          - entity: switch.leddriver_00_27
            name: _27
        title: leddriver-00-2x
        state_color: true
      - type: entities
        entities:
          - entity: switch.leddriver_00_30
            name: _30
          - entity: switch.leddriver_00_31
            name: _31
          - entity: switch.leddriver_00_32
            name: _32
          - entity: switch.leddriver_00_33
            name: _33
          - entity: switch.leddriver_00_34
            name: _34
          - entity: switch.leddriver_00_35
            name: _35
          - entity: switch.leddriver_00_36
            name: _36
          - entity: switch.leddriver_00_37
            name: _37
        title: leddriver-00-3x
        state_color: true
      - type: entities
        entities:
          - entity: switch.leddriver_00_40
            name: _40
          - entity: switch.leddriver_00_41
            name: _41
          - entity: switch.leddriver_00_42
            name: _42
          - entity: switch.leddriver_00_43
            name: _43
          - entity: switch.leddriver_00_44
            name: _44
          - entity: switch.leddriver_00_45
            name: _45
          - entity: switch.leddriver_00_46
            name: _46
          - entity: switch.leddriver_00_47
            name: _47
        title: leddriver-00-4x
        state_color: true
      - type: entities
        entities:
          - entity: switch.leddriver_00_50
            name: _50
          - entity: switch.leddriver_00_51
            name: _51
          - entity: switch.leddriver_00_52
            name: _52
          - entity: switch.leddriver_00_53
            name: _53
          - entity: switch.leddriver_00_54
            name: _54
          - entity: switch.leddriver_00_55
            name: _55
          - entity: switch.leddriver_00_56
            name: _56
          - entity: switch.leddriver_00_57
            name: _57
        title: leddriver-00-5x
        state_color: true
      - type: entities
        entities:
          - entity: switch.leddriver_00_60
            name: _60
          - entity: switch.leddriver_00_61
            name: _61
          - entity: switch.leddriver_00_62
            name: _62
          - entity: switch.leddriver_00_63
            name: _63
          - entity: switch.leddriver_00_64
            name: _64
          - entity: switch.leddriver_00_65
            name: _65
          - entity: switch.leddriver_00_66
            name: _66
          - entity: switch.leddriver_00_67
            name: _67
        title: leddriver-00-6x
        state_color: true
      - type: entities
        entities:
          - entity: switch.leddriver_00_70
            name: _70
          - entity: switch.leddriver_00_71
            name: _71
          - entity: switch.leddriver_00_72
            name: _72
          - entity: switch.leddriver_00_73
            name: _73
          - entity: switch.leddriver_00_74
            name: _74
          - entity: switch.leddriver_00_75
            name: _75
          - entity: switch.leddriver_00_76
            name: _76
          - entity: switch.leddriver_00_77
            name: _77
        title: leddriver-00-7x
        state_color: true
      - type: entities
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

### Occupied

|||
|:---:|:---:|
|![Occupied-Hp-xx](./images/Skærmbillede%20fra%202024-02-03%2009-28-41.png)|![LedDriver-00](./images/Skærmbillede%20fra%202024-02-03%2009-28-52.png)|

```code
type: entities
entities:
  - entity: binary_sensor.occupied_hp_00
    name: _00
  - entity: binary_sensor.occupied_hp_01
    name: _01
  - entity: binary_sensor.occupied_hp_02
    name: _02
  - entity: binary_sensor.occupied_hp_03
    name: _03
  - entity: binary_sensor.occupied_hp_04
    name: _04
  - entity: binary_sensor.occupied_hp_05
    name: _05
  - entity: binary_sensor.occupied_hp_06
    name: _06
  - entity: binary_sensor.occupied_hp_07
    name: _07
title: Occupied-Hp-0x

```

```code
type: entities
entities:
  - entity: update.occupied_hp_firmware
    name: Firmware
  - entity: button.occupied_hp_restart_occupied_hp
    name: Restart occupied-hp
  - entity: sensor.occupied_hp_connected_bssid_occupied_hp
    name: Connected BSSID occupied-hp
  - entity: sensor.occupied_hp_connected_ssid_occupied_hp
    name: Connected SSID occupied-hp
  - entity: sensor.occupied_hp_ip_address_occupied_hp
    name: IP Address occupied-hp
  - entity: sensor.occupied_hp_mac_wifi_address_occupied_hp
    name: Mac Wifi Address occupied-hp
title: Occupied-Hp
```

### Track Reserved

|||
|:---:|:---:|
|![Track Reserved-xx](./images/Skærmbillede%20fra%202024-02-03%2009-31-35.png)||

```code
type: entities
entities:
  - entity: input_boolean.track_reserved_00_00
  - entity: input_boolean.track_reserved_00_01
  - entity: input_boolean.track_reserved_00_02
  - entity: input_boolean.track_reserved_00_03
  - entity: input_boolean.track_reserved_00_04
  - entity: input_boolean.track_reserved_00_05
  - entity: input_boolean.track_reserved_00_06
  - entity: input_boolean.track_reserved_00_07
show_header_toggle: true
state_color: true
title: Track Reserved 00_0x
```
