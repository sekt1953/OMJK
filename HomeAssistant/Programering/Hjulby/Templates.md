# Hlulby

## Templates

```yaml
- trigger:
    # Spor 1
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_00
      to: null
      id: Ju_A61
      variables:
        red_ent: light.ju_pl_00_5E
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_01
      to: null
      id: Ju_M12
      variables:
        red_ent: light.ju_pl_00_5C
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_0f
      to: null
      id: Ju_01
      variables:
        red_ent: light.ju_pl_00_5b
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_02
      to: null
      id: Ju_105b
      variables:
        red_ent: light.ju_pl_00_5B
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_10
      to: null
      id: Ju_03
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_03
      to: null
      id: Ju_04
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_11
      to: null
      id: Ju_101b
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_04
      to: null
      id: Ju_06
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_0c
      to: null
      id: Ju_C12
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_1a
      to: null
      id: Ju_C61
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    # Spor 2
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_19
      to: null
      id: Ju_D61
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_0b
      to: null
      id: Ju_A12
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_15
      to: null
      id: Ju_14
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_07
      to: null
      id: Ju_101a
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_14
      to: null
      id: Ju_102a
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_06
      to: null
      id: Ju_11
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_13
      to: null
      id: Ju_10
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_05
      to: null
      id: Ju_105a
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_12
      to: null
      id: Ju_08
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_0e
      to: null
      id: Ju_K12
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    - trigger: state
      entity_id:
        - binary_sensor.ju_sb_00_0d
      to: null
      id: Ju_B61
      variables:
        red_ent: light.ju_pl_00_
        green_ent: light.ju_pl_00_
    # Spor 3
  sensor:
    - name: ju-isolation
      state: "{{ trigger.id }},{{ trigger.to_state.state }}"
      attributes:
        trigger-id: "{{ trigger.id }}"
        event-to-map: "{{ trigger.to_state.state }}"
        event-from-map: "{{ trigger.from_state.state }}"
        target-red-map: "{{ red_ent }}"
        target-green-map: "{{ green_ent }}"
```

```
```