# Vejledning til Sporskiftestyrings firmware

## Home Assistant settings

### configuration.yaml

* opret [Input text helper](https://www.home-assistant.io/integrations/input_text) til at sende list af sporskifter som skal omstilles.

```yaml
input_text:
  name: Ju_Sporskifte
  initial: { "108a+", "108b+", "109b-" }
  min: 0
  max: 100
  mode: text
```

## ESPHome settings

### sensor

* AI - Forespørelse:
  * esphome how to react on change of homeassistant entity
* AI - Svar:
  * To react to changes of a Home Assistant entity inside ESPHome, you must import the entity into your ESPHome configuration using a Home Assistant tracking platform (such as sensor, binary_sensor, text_sensor, or switch) and attach an automation trigger to it.
  * Use the ESPHome Home Assistant Text Sensor platform to track entities outputting text (e.g., weather states, media player statuses, or user profiles). Use the on_value trigger to catch changes.
* Min Løsning:

```yaml
text_sensor:
  - platform: homeassistant
    id:
    entity_id:
    on_value:
      then:
        - logger.log: 
          format: "Some text: %s"
          args: [ 'x.c_str()' ]
```
