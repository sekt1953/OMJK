# Lovelace Hjulby

## Test setup

```yaml
views:
  - path: default_view
    title: Home
    cards:
      - type: entities
        entities:
          - entity: switch.iso1_00
            name: _00
          - entity: switch.iso1_01
            name: _01
          - entity: switch.iso1_02
            name: _02
          - entity: switch.iso1_03
            name: _03
          - entity: switch.iso1_04
            name: _04
          - entity: switch.iso1_05
            name: _05
          - entity: switch.iso1_06
            name: _06
          - entity: switch.iso1_07
            name: _07
          - entity: switch.iso1_10
            name: _10
          - entity: switch.iso1_11
            name: _11
          - entity: switch.iso1_12
            name: _12
          - entity: switch.iso1_13
            name: _13
          - entity: switch.iso1_14
            name: _14
          - entity: switch.iso1_15
            name: _15
          - entity: switch.iso1_16
            name: _16
          - entity: switch.iso1_17
            name: _17
          - entity: switch.iso1_20
            name: _20
          - entity: switch.iso1_21
            name: _21
          - entity: switch.iso1_22
            name: _22
          - entity: switch.iso1_23
            name: _23
          - entity: switch.iso1_24
            name: _24
          - entity: switch.iso1_25
            name: _25
          - entity: switch.iso1_26
            name: _26
          - entity: switch.iso1_27
            name: _27
          - entity: switch.iso1_30
            name: _30
          - entity: switch.iso1_31
            name: _31
          - entity: switch.iso1_32
            name: _32
          - entity: switch.iso1_33
            name: _33
          - entity: switch.iso1_34
            name: _34
          - entity: switch.iso1_35
            name: _35
          - entity: switch.iso1_36
            name: _36
          - entity: switch.iso1_37
            name: _37
        title: Iso1
      - type: entities
        entities:
          - entity: binary_sensor.iso1_40
            name: _40
          - entity: binary_sensor.iso1_41
            name: _41
          - entity: binary_sensor.iso1_42
            name: _42
          - entity: binary_sensor.iso1_43
            name: _43
          - entity: binary_sensor.iso1_44
            name: _44
          - entity: binary_sensor.iso1_45
            name: _45
          - entity: binary_sensor.iso1_46
            name: _46
          - entity: binary_sensor.iso1_47
            name: _47
          - entity: binary_sensor.iso1_50
            name: _50
          - entity: binary_sensor.iso1_51
            name: _51
          - entity: binary_sensor.iso1_52
            name: _52
          - entity: binary_sensor.iso1_53
            name: _53
          - entity: binary_sensor.iso1_54
            name: _54
          - entity: binary_sensor.iso1_55
            name: _55
          - entity: binary_sensor.iso1_56
            name: _56
          - entity: binary_sensor.iso1_57
            name: _57
          - entity: binary_sensor.iso1_60
            name: _60
          - entity: binary_sensor.iso1_61
            name: _61
          - entity: binary_sensor.iso1_62
            name: _62
          - entity: binary_sensor.iso1_63
            name: _63
          - entity: binary_sensor.iso1_64
            name: _64
          - entity: binary_sensor.iso1_65
            name: _65
          - entity: binary_sensor.iso1_66
            name: _66
          - entity: binary_sensor.iso1_67
            name: _67
          - entity: binary_sensor.iso1_70
            name: _70
          - entity: binary_sensor.iso1_71
            name: _71
          - entity: binary_sensor.iso1_72
            name: _72
          - entity: binary_sensor.iso1_73
            name: _73
          - entity: binary_sensor.iso1_74
            name: _74
          - entity: binary_sensor.iso1_75
            name: _75
          - entity: binary_sensor.iso1_76
            name: _76
          - entity: binary_sensor.iso1_77
            name: _77
        title: Iso1
      - type: entity
        entity: sensor.ju_isolation
      - type: entity
        entity: sensor.ju_isolation
        attribute: trigger-id
        name: Trigger ID
        grid_options:
          columns: 24
          rows: 2
        state_color: false
      - type: entity
        entity: sensor.ju_isolation
        attribute: event-to-map
        name: 'Event to '
        grid_options:
          columns: 24
          rows: 2
        state_color: false
      - type: entity
        entity: sensor.ju_isolation
        attribute: event-from-map
        name: Event from
        grid_options:
          columns: 24
          rows: 2
        state_color: false
      - type: entity
        entity: sensor.ju_isolation
        attribute: target-red-map
        name: Target Red
        grid_options:
          columns: 24
          rows: 2
        state_color: false
      - type: entity
        entity: sensor.ju_isolation
        attribute: target-green-map
        name: Target Green
        grid_options:
          columns: 24
          rows: 2
        state_color: false
      - type: entities
        entities:
          - entity: button.iso1_restart_iso1
            name: Restart iso1
          - entity: sensor.iso1_dns_address_iso1
            name: DNS Address iso1
          - entity: sensor.iso1_ip_address_iso1
            name: IP Address iso1
          - entity: sensor.iso1_mac_address_iso1
            name: MAC Address iso1
        title: Iso1

```
