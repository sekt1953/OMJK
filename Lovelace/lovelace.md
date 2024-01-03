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
