# Access Home Assistant helpers in ESPHome

by using the homeassistant platform for sensors or text sensors. Define an id for the entity in your YAML, then access its value in real-time within lambda functions using id(sensor_id).state. Use input_number as a sensor and input_text as a text_sensor.

Accessing Helper Number (input_number)

Use the sensor component with platform: homeassistant to read an input_number 
helper from Home Assistant.

yaml

sensor:
  - platform: homeassistant
    id: hasensor1
    entity_id: input_number.helper_number_1
    
# Usage in a lambda (e.g., in a script or automation)
on_press:
  - delay: !lambda 'return id(hasensor1).state;'

Vær forsigtig med at bruge denne kode.

Accessing Helper Text (input_text)

Use the text_sensor component to read an input_text helper.

yaml

text_sensor:
  - platform: homeassistant
    id: hatext1
    entity_id: input_text.helper_text_1

Vær forsigtig med at bruge denne kode.

Best Practices & Tips

Global Variables: To make helper values available even if Home Assistant is offline, store the on_value of the sensor into a global variable.

Two-Way Sync: While the above reads HA to ESPHome, you can use lambda functions to write to global variables for tighter integration.

Types: Ensure numbers are handled as float and text as std::string within lambdas.

Debugging: If values are not updating, review the logs using the ESPHome CLI.

For more detailed information, you can consult the official documentation on the 
ESPHome text_sensor component and ESPHome core configuration.

