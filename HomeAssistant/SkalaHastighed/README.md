# How to calculate train speed in km scale 1:45

## AI

* At beregne hastigheden på et modeltog i skala 1:45 (også kendt som Spor 0)kræver, at vi tager højde for skalafaktoren, så toget bevæger sig på en måde,der ser realistisk ud i forhold til virkeligheden.  
* Her er de to metoder til at gøre det:

1. Beregning af "Skalahastighed" (Virkelighed til Model)
Hvis du ved, hvor hurtigt et rigtigt tog kører (f.eks. 100 km/t), og du vil vide, hvor hurtigt din model skal køre for at se realistisk ud, bruger du denne formel:

![](./Image/Skærmbillede%20fra%202026-03-03%2015-57-47.png)

Eksempel:  
Et tog kører 90 km/t i virkeligheden. I skala 1:45 skal modellen køre:

![](./Image/Skærmbillede%20fra%202026-03-03%2015-57-58.png)

2. Praktisk måling på din bane (Model til Virkelighed)
Dette er den mest almindelige metode. Du måler, hvor lang tid det tager toget at køre en bestemt distance, og regner det om til "rigtige" kilometer i timen.
Fremgangsmåde:
   1. Opmål en strækning på din bane (f.eks. 2 meter).
   2. Tag tid med et stopur på, hvor mange sekunder det tager toget at køre distancen.
   3. Brug følgende formel:  

![2015-39-59.png](./Image/Skærmbillede%20fra%202026-03-03%2015-39-59.png)

Hvor 3,6 er konverteringsfaktoren fra m/s til km/t, og 45 er din skala.
Eksempel:
Hvis dit tog i skala 1:45 bruger 5 sekunder på at køre 2 meter:  

![2015-40-24.png](./Image/Skærmbillede%20fra%202026-03-03%2015-40-24.png)

(Toget kører altså med en hastighed, der svarer til ca. 65 km/t i virkeligheden).  

* Hurtig-tabel for skala 1:45  
Her er en oversigt over, hvor lang tid det bør tage din model at køre 1 meter, hvis det skal svare til en bestemt hastighed i virkeligheden:
	Tid pr. 1 meter (Skala 1:45)

|Virkelig hastighed|Tid pr. 1 meter (Skala 1:45)|
|---:|---:|
|40 km/t|4,05 sekunder|
|60 km/t|2,70 sekunder|
|80 km/t|2,03 sekunder|
|100 km/t|1,62 sekunder|
|120 km/t|1,35 sekunder|

* Et lille tip til realismen
  * Mange modeltogs-entusiaster synes faktisk, at skalahastighed ser "for hurtigt" ud for det menneskelige øje. Man vælger ofte at køre lidt langsommere end den matematiske skalahastighed for at give toget mere tyngde og realisme.
  * Vil du have hjælp til at lave en tabel, der passer præcis til længden på din skinne-strækning?

## Home Assistant

* To calculate the time between two events in Home Assistant, use a Trigger-based Template Sensor to compare the .last_changed timestamps of two entities. Calculate the difference using Jinja2 templates, such as {{ (states.sensor.end.last_changed - states.sensor.start.last_changed).total_seconds() }}.

* Key Methods to Calculate Time Between Events
Trigger-based Template Sensor (Best Method): This method creates a new sensor that updates only when specific events occur.

```yaml
# Example: Time between turning on (start) and off (end)
template:
  - trigger:
      - platform: state
        entity_id: switch.device
        from: "off"
        to: "on"
        id: "start"
      - platform: state
        entity_id: switch.device
        from: "on"
        to: "off"
        id: "end"
    sensor:
      - name: Time Between Events
        state: >-
          {% if trigger.id == "end" %}
            {{ (now() - trigger.from_state.last_changed).total_seconds() }}
          {% else %}
            {{ states('sensor.time_between_events') }}
          {% endif %}
        unit_of_measurement: "s"
```

* Comparing .last_changed Attributes: If you have two different sensors,you can subtract their last_changed times directly:

```yaml
{{ (states.sensor.event_two.last_changed - states.sensor.event_one.last_changed).total_seconds() }}
```

* Tips
  * Convert to Seconds: Use .total_seconds() to get the difference in a usable numeric format.
  * Round Values: Use | round(2) to format the output.
  * Time Formatting: Use relative_time() to display time in a readable format (e.g., "5 minutes").

* [Relative Time Plus](https://github.com/TheFes/relative-time-plus?tab=readme-ov-file#relative-time-plus)
* [Easy Time](https://github.com/Petro31/easy-time-jinja#easy-time)