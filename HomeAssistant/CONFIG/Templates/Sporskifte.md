# Template

## triggerdelen

```yaml
- trigger:
    - trigger: state
      entity_id:
        - binary_sensor.ju_pl_01_07
      to: "on"
      id: 101+
      for:
        hours: 0
        minutes: 0
        seconds: 1
      variables:
        Motor_A01_ent:
        Motor_A02_ent:
        Motor_B01_ent:
        Motor_B02_ent:
        Retur_A01_ent:
        Retur_A02_ent:
        Retur_B01_ent:
        Retur_B02_ent:
        Led_A_Group_ent:
        Led_B_Group_ent:
        Led_AB_Group_ent:
        Spor_A_Besat_ent:
        Spor_B_Besat_ent:
        MasterPult_On_ent: binary_sensor.ju_pl_01_17
        LocalPult_On_ent: binary_sensor.ju_pl_01_50
- trigger:
    - trigger: state
      entity_id:
        - binary_sensor.ju_pl_01_06
      to: "on"
      id: 101-
      for:
        hours: 0
        minutes: 0
        seconds: 1
      variables:
        Motor_A01_ent:
        Motor_A02_ent:
        Motor_B01_ent:
        Motor_B02_ent:
        Retur_A01_ent:
        Retur_A02_ent:
        Retur_B01_ent:
        Retur_B02_ent:
        Led_A_Group_ent:
        Led_B_Group_ent:
        Led_AB_Group_ent:
        Spor_A_Besat_ent:
        Spor_B_Besat_ent:
        MasterPult_On_ent: binary_sensor.ju_pl_01_17
        LocalPult_On_ent: binary_sensor.ju_pl_01_50
```

## conditon delen

```yaml
  condition:
    - condition: or
      conditions:
        - condition: and
          conditions:
            - condition: template
              value_template: >-
                {{ trigger.to_state.last_updated -
                trigger.from_state.last_updated  < as_timedelta("00:00:01")
                }}
            - condition: template
              value_template: "{{ trigger.to_state.state == 'off'}}"
        - condition: and
          conditions:
            - condition: template
              value_template: >-
                {{ trigger.to_state.last_updated -
                trigger.from_state.last_updated  >= as_timedelta("00:00:01")
                    }}
            - condition: template
              value_template: "{{ trigger.to_state.state == 'on'}}"
```

## Sensor delen

```yaml
  sensor:
    - name: LK-Pushbutton-Pressed
      state: "{{ trigger.id }},{{now().strftime('%H:%M:%S')}}"
      attributes:
        trigger-id: "{{ trigger.id }}"
        Motor_A01_Map: "{{ Motor_A01_ent: }}"
        Motor_A02_Map: "{{ Motor_A02_ent: }}"
        "{{ Motor_B01_ent: }}"
        "{{ Motor_B02_ent: }}"
        "{{ Retur_A01_ent: }}"
        "{{ Retur_A02_ent: }}"
        "{{ Retur_B01_ent: }}"
        "{{ Retur_B02_ent: }}"
        "{{ Led_A_Group_ent: }}"
        "{{ Led_B_Group_ent: }}"
        "{{ Led_AB_Group_ent: }}"
        "{{ Spor_A_Besat_ent: }}"
        "{{ Spor_B_Besat_ent: }}"
        "{{ MasterPult_On_ent }}"
        "{{ LocalPult_On_ent }}"
```