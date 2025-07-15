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
