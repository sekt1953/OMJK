# Automations

## /CONFIG/automations.yaml

### Train occupied sensor 00_00

```yaml
- id: '1683045478482'
  alias: Train occupied sensor 00_00
  description: ''
  use_blueprint:
    path: train/train_occupied_sensor.yaml
    input:
      reserved_sensor: input_boolean.track_reserved_00_00
      occupied_sensor: binary_sensor.tracksensor_00_00
      green_light_target:
        entity_id: switch.trackdisplay_00_00
      red_light_target:
        entity_id: switch.trackdisplay_00_10
```

### track_section_occupied

```yaml
- id: '1704825729184'
  alias: track_section_occupied
  description: ''
  trigger:
  - platform: state
    entity_id:
    - input_boolean.track_reserved_00_00
    from:
    id: track joins status change
    alias: When track train road joins status change
  condition: []
  action:
  - choose:
    - conditions:
      - condition: trigger
        id:
        - track joins status change
      - condition: state
        entity_id: input_boolean.track_reserved_00_00
        state: 'on'
      sequence:
      - service: switch.turn_on
        metadata: {}
        data: {}
        target:
          entity_id:
          - switch.leddriver_02_00
      alias: Track join train-road
    - conditions:
      - condition: trigger
        id:
        - track joins status change
      - condition: state
        entity_id: input_boolean.track_reserved_00_00
        state: 'off'
      sequence:
      - service: switch.turn_off
        metadata: {}
        data: {}
        target:
          entity_id:
          - switch.leddriver_02_00
      alias: Track train-road emergency_dissolves
  mode: single
```
