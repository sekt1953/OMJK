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

![Home](./images/Skærmbillede%20fra%202024-01-06%2014-11-27.png)

```code
    title: Home
    cards:
      - type: vertical-stack
        cards:
          - type: horizontal-stack
            cards:
              - type: entities
                entities:
                  - person.omjk
                state_color: true
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
                show_state: false
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

```code
  - title: LedDriver-01
    path: leddriver-01
    subview: true
    badges: []
    cards:
      - type: entities
        entities:
          - entity: switch.leddriver_01_00
            name: _00
          - entity: switch.leddriver_01_01
            name: _01
          - entity: switch.leddriver_01_02
            name: _02
          - entity: switch.leddriver_01_03
            name: _03
          - entity: switch.leddriver_01_04
            name: _04
          - entity: switch.leddriver_01_05
            name: _05
          - entity: switch.leddriver_01_06
            name: _06
          - entity: switch.leddriver_01_07
            name: _07
        title: leddriver-01-0x
      - type: entities
        entities:|||
|:---:|:---:|
|![LedDriver-00-xx](./images/Skærmbillede%20fra%202024-01-06%2012-04-10.png)|![LedDriver-00](./images/Skærmbillede%20fra%202024-01-06%2012-10-11.png)|

          - entity: switch.leddriver_01_10
            name: _10
          - entity: switch.leddriver_01_11
            name: _11
          - entity: switch.leddriver_01_12
            name: _12
          - entity: switch.leddriver_01_13
            name: _13
          - entity: switch.leddriver_01_14
            name: _14
          - entity: switch.leddriver_01_15
            name: _15
          - entity: switch.leddriver_01_16
            name: _16
          - entity: switch.leddriver_01_17
            name: _17
        title: leddriver-01-1x
      - type: entities
        entities:
          - entity: switch.leddriver_01_20
            name: _20
          - entity: switch.leddriver_01_21
            name: _21
          - entity: switch.leddriver_01_22
            name: _22
          - entity: switch.leddriver_01_23
            name: _23
          - entity: switch.leddriver_01_24
            name: _24
          - entity: switch.leddriver_01_25
            name: _25
          - entity: switch.leddriver_01_26
            name: _26
          - entity: switch.leddriver_01_27
            name: _27
        title: leddriver-01-2x
      - type: entities
        entities:
          - entity: switch.leddriver_01_30
            name: _30
          - entity: switch.leddriver_01_31
            name: _31
          - entity: switch.leddriver_01_32
            name: _32
          - entity: switch.leddriver_01_33
            name: _33
          - entity: switch.leddriver_01_34
            name: _34
          - entity: switch.leddriver_01_35
            name: _35
          - entity: switch.leddriver_01_36
            name: _36
          - entity: switch.leddriver_01_37
            name: _37
        title: leddriver-01-3x
      - type: entities
        entities:
          - entity: switch.leddriver_01_40
            name: _40
          - entity: switch.leddriver_01_41
            name: _41
          - entity: switch.leddriver_01_42
            name: _42
          - entity: switch.leddriver_01_43
            name: _43
          - entity: switch.leddriver_01_44
            name: _44
          - entity: switch.leddriver_01_45
            name: _45
          - entity: switch.leddriver_01_46
            name: _46
          - entity: switch.leddriver_01_47
            name: _47
        title: leddriver-01-4x
      - type: entities
        entities:
          - entity: switch.leddriver_01_50
            name: _50
          - entity: switch.leddriver_01_51
            name: _51
          - entity: switch.leddriver_01_52
            name: _52
          - entity: switch.leddriver_01_53
            name: _53
          - entity: switch.leddriver_01_54
            name: _54
          - entity: switch.leddriver_01_55
            name: _55
          - entity: switch.leddriver_01_56
            name: _56
          - entity: switch.leddriver_01_57
            name: _57
        title: leddriver-01-5x
      - type: entities
        entities:
          - entity: switch.leddriver_01_60
            name: _60
          - entity: switch.leddriver_01_61
            name: _61
          - entity: switch.leddriver_01_62
            name: _62
          - entity: switch.leddriver_01_63
            name: _63
          - entity: switch.leddriver_01_64
            name: _64
          - entity: switch.leddriver_01_65
            name: _65
          - entity: switch.leddriver_01_66
            name: _66
          - entity: switch.leddriver_01_67
            name: _67
        title: leddriver-01-6x
      - type: entities
        entities:
          - entity: switch.leddriver_01_70
            name: _70
          - entity: switch.leddriver_01_71
            name: _71
          - entity: switch.leddriver_01_72
            name: _72
          - entity: switch.leddriver_01_73
            name: _73
          - entity: switch.leddriver_01_74
            name: _74
          - entity: switch.leddriver_01_75
            name: _75
          - entity: switch.leddriver_01_76
            name: _76
          - entity: switch.leddriver_01_77
            name: _77
        title: leddriver-01-7x
      - type: entities
        entities:
          - entity: update.leddriver_01_firmware
            name: Firmware
          - entity: button.leddriver_01_restart_leddriver_01
            name: Restart leddriver-01
          - entity: sensor.leddriver_01_connected_bssid_leddriver_01
            name: Connected BSSID leddriver-01
          - entity: sensor.leddriver_01_connected_ssid_leddriver_01
            name: Connected SSID leddriver-01
          - entity: sensor.leddriver_01_ip_address_leddriver_01
            name: IP Address leddriver-01
          - entity: sensor.leddriver_01_mac_wifi_address_leddriver_01
            name: Mac Wifi Address leddriver-01
        title: leddriver-01
  ```

```code
- title: LedDriver-02
    path: leddriver-02
    subview: true
    badges: []
    cards:
      - type: entities
        entities:
          - entity: switch.leddriver_02_00
            name: _00
          - entity: switch.leddriver_02_01
            name: _01
          - entity: switch.leddriver_02_02
            name: _02
          - entity: switch.leddriver_02_03
            name: _03
          - entity: switch.leddriver_02_04
            name: _04
          - entity: switch.leddriver_02_05
            name: _05
          - entity: switch.leddriver_02_06
            name: _06
          - entity: switch.leddriver_02_07
            name: _07
        title: leddriver-02-0x
      - type: entities
        entities:
          - entity: switch.leddriver_02_10
            name: _10
          - entity: switch.leddriver_02_11
            name: _11
          - entity: switch.leddriver_02_12
            name: _12
          - entity: switch.leddriver_02_13
            name: _13
          - entity: switch.leddriver_02_14
            name: _14
          - entity: switch.leddriver_02_15
            name: _15
          - entity: switch.leddriver_02_16
            name: _16
          - entity: switch.leddriver_02_17
            name: _17
        title: leddriver-02-1x
      - type: entities
        entities:
          - entity: switch.leddriver_02_20
            name: _20
          - entity: switch.leddriver_02_21
            name: _21
          - entity: switch.leddriver_02_22
            name: _22
          - entity: switch.leddriver_02_23
            name: _23
          - entity: switch.leddriver_02_24
            name: _24
          - entity: switch.leddriver_02_25
            name: _25
          - entity: switch.leddriver_02_26
            name: _26
          - entity: switch.leddriver_02_27
            name: _27
        title: leddriver-02-2x
      - type: entities
        entities:
          - entity: switch.leddriver_02_30
            name: _30
          - entity: switch.leddriver_02_31
            name: _31
          - entity: switch.leddriver_02_32
            name: _32
          - entity: switch.leddriver_02_33
            name: _33
          - entity: switch.leddriver_02_34
            name: _34
          - entity: switch.leddriver_02_35
            name: _35
          - entity: switch.leddriver_02_36
            name: _36
          - entity: switch.leddriver_02_37
            name: _37
        title: leddriver-02-3x
      - type: entities
        entities:
          - entity: switch.leddriver_02_40
            name: _40
          - entity: switch.leddriver_02_41
            name: _41
          - entity: switch.leddriver_02_42
            name: _42
          - entity: switch.leddriver_02_43
            name: _43
          - entity: switch.leddriver_02_44
            name: _44
          - entity: switch.leddriver_02_45
            name: _45
          - entity: switch.leddriver_02_46
            name: _46
          - entity: switch.leddriver_02_47
            name: _47
        title: leddriver-02-4x
      - type: entities
        entities:
          - entity: switch.leddriver_02_50
            name: _50
          - entity: switch.leddriver_02_51
            name: _51
          - entity: switch.leddriver_02_52
            name: _52
          - entity: switch.leddriver_02_53
            name: _53
          - entity: switch.leddriver_02_54
            name: _54
          - entity: switch.leddriver_02_55
            name: _55
          - entity: switch.leddriver_02_56
            name: _56
          - entity: switch.leddriver_02_57
            name: _57
        title: leddriver-02-5x
      - type: entities
        entities:
          - entity: switch.leddriver_02_60
            name: _60
          - entity: switch.leddriver_02_61
            name: _61
          - entity: switch.leddriver_02_62
            name: _62
          - entity: switch.leddriver_02_63
            name: _63
          - entity: switch.leddriver_02_64
            name: _64
          - entity: switch.leddriver_02_65
            name: _65
          - entity: switch.leddriver_02_66
            name: _66
          - entity: switch.leddriver_02_67
            name: _67
        title: leddriver-02-6x
      - type: entities
        entities:
          - entity: switch.leddriver_02_70
            name: _70
          - entity: switch.leddriver_02_71
            name: _71
          - entity: switch.leddriver_02_72
            name: _72
          - entity: switch.leddriver_02_73
            name: _73
          - entity: switch.leddriver_02_74
            name: _74
          - entity: switch.leddriver_02_75
            name: _75
          - entity: switch.leddriver_02_76
            name: _76
          - entity: switch.leddriver_02_77
            name: _77
        title: leddriver-02-7x
      - type: entities
        entities:
          - entity: update.leddriver_02_firmware
            name: Firmware
          - entity: button.leddriver_02_restart_leddriver_02
            name: Restart leddriver-02
          - entity: sensor.leddriver_02_connected_bssid_leddriver_02
            name: Connected BSSID leddriver-02
          - entity: sensor.leddriver_02_connected_ssid_leddriver_02
            name: Connected SSID leddriver-02
          - entity: sensor.leddriver_02_ip_address_leddriver_02
            name: IP Address leddriver-02
          - entity: sensor.leddriver_02_mac_wifi_address_leddriver_02
            name: Mac Wifi Address leddriver-02
        title: leddriver-02

```


