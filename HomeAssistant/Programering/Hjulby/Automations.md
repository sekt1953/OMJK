# Hjulby

## Automations

```yaml
alias: Hjulby Spor Besat
description: ""
triggers:
  - trigger: state
    entity_id:
      - sensor.ju_isolation
    to: null
conditions: []
actions:
  - action: "{{ state_attr('sensor.ju_isolation','event-map')}}"
    metadata: {}
    data: {}
    target:
      entity_id: "{{ state_attr('sensor.ju_isolation','target-green-map') }}"
  - choose:
      - conditions:
          - condition: state
            entity_id: sensor.ju_isolation
            attribute: event-map
            state: besat
        sequence:
          - action: light.turn_on
            metadata: {}
            data: {}
            target:
              entity_id: "{{ state_attr('sensor.ju_isolation','target-red-map') }}"
mode: single
```

```yaml
alias: Sporskiftetest_002
description: ""
triggers:
  - trigger: state
    entity_id:
      - binary_sensor.ju_udvendig_betjeningsskab_00
    from: "off"
    to: "on"
    id: 101+
  - trigger: state
    entity_id:
      - binary_sensor.ju_udvendig_betjeningsskab_02
    from: "off"
    to: "on"
    id: 101-
conditions: []
actions:
  - choose:
      - conditions:
          - condition: trigger
            id:
              - 101+
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id:
                - light.ju_udvendig_betjeningsskab_section_01
                - light.ju_udvendig_betjeningsskab_section_02
                - light.ju_udvendig_betjeningsskab_section_03
          - action: switch.turn_off
            metadata: {}
            data: {}
            target:
              entity_id:
                - switch.ju_sp_tp_101a1
                - switch.ju_sp_tp_101a2
                - switch.ju_sp_tp_101b1
                - switch.ju_sp_tp_101b2
          - action: switch.turn_on
            metadata: {}
            data: {}
            target:
              entity_id:
                - switch.ju_sp_tp_101a1
          - delay:
              hours: 0
              minutes: 0
              seconds: 0
              milliseconds: 500
          - delay:
              hours: 0
              minutes: 0
              seconds: 3
              milliseconds: 0
          - action: switch.turn_on
            metadata: {}
            data: {}
            target:
              entity_id: switch.ju_sp_tp_101b2
          - delay:
              hours: 0
              minutes: 0
              seconds: 2
              milliseconds: 0
          - action: light.turn_on
            metadata: {}
            data:
              transition: 0
              color_temp_kelvin: 6500
              brightness_pct: 39
            target:
              entity_id:
                - light.ju_udvendig_betjeningsskab_section_01
                - light.ju_udvendig_betjeningsskab_section_03
      - conditions:
          - condition: trigger
            id:
              - 101-
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id:
                - light.ju_udvendig_betjeningsskab_section_01
                - light.ju_udvendig_betjeningsskab_section_02
                - light.ju_udvendig_betjeningsskab_section_03
          - action: switch.turn_off
            metadata: {}
            data: {}
            target:
              entity_id:
                - switch.ju_sp_tp_101a1
                - switch.ju_sp_tp_101a2
                - switch.ju_sp_tp_101b1
                - switch.ju_sp_tp_101b2
          - action: switch.turn_on
            metadata: {}
            data: {}
            target:
              entity_id:
                - switch.ju_sp_tp_101a2
          - delay:
              hours: 0
              minutes: 0
              seconds: 0
              milliseconds: 500
          - delay:
              hours: 0
              minutes: 0
              seconds: 3
              milliseconds: 0
          - action: switch.turn_on
            metadata: {}
            data: {}
            target:
              entity_id: switch.ju_sp_tp_101b1
          - delay:
              hours: 0
              minutes: 0
              seconds: 2
              milliseconds: 0
          - action: light.turn_on
            metadata: {}
            data:
              transition: 0
              color_temp_kelvin: 6500
              brightness_pct: 39
            target:
              entity_id:
                - light.ju_udvendig_betjeningsskab_section_02
mode: queued
max: 10
```

