# Sporskifte

## Enties

### Sporskifte Hjulby Pult Tryk Entites:

```data
101+	binary_sensor.ju_pl_01_07
101-	binary_sensor.ju_pl_01_06
A12	binary_sensor.ju_pl_01_17	Aktiv når sporskifte er betjent fra hovedpult
B1	binary_sensor.ju_pl_01_50	Aktiv når sporskifte er betjent fra rangerpult

102+	binary_sensor.ju_pl_01_05
102-	binary_sensor.ju_pl_01_04
A13	binary_sensor.ju_pl_01_16	Aktiv når sporskifte er betjent fra hovedpult
B2	binary_sensor.ju_pl_01_67

S3
A16	binary_sensor.ju_pl_01_13	Aktiv når sporskifte er betjent fra hovedpult
B5	binary_sensor.ju_pl_01_64

104+	binary_sensor.ju_pl_01_02
104-	binary_sensor.ju_pl_01_03
A14	binary_sensor.ju_pl_01_15	Aktiv når sporskifte er betjent fra hovedpult
B3	binary_sensor.ju_pl_01_66

105+	binary_sensor.ju_pl_01_01
105-	binary_sensor.ju_pl_01_00
A15	binary_sensor.ju_pl_01_14	Aktiv når sporskifte er betjent fra hovedpult
B4	binary_sensor.ju_pl_01_65
```

### Sporskifte Hjulby Pult Led Entites:

```data
```

## Template

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