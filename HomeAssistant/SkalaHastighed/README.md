# how to calculate train speed in km scale 1:45

## AI

* At beregne hastigheden på et modeltog i skala 1:45 (også kendt som Spor 0)kræver, at vi tager højde for skalafaktoren, så toget bevæger sig på en måde,der ser realistisk ud i forhold til virkeligheden.  
* Her er de to metoder til at gøre det:

1. Beregning af "Skalahastighed" (Virkelighed til Model)
Hvis du ved, hvor hurtigt et rigtigt tog kører (f.eks. 100 km/t), og du vil vide, hvor hurtigt din model skal køre for at se realistisk ud, bruger du denne formel:

Eksempel:
Et tog kører 90 km/t i virkeligheden. I skala 1:45 skal modellen køre:

2. Praktisk måling på din bane (Model til Virkelighed)
Dette er den mest almindelige metode. Du måler, hvor lang tid det tager toget at køre en bestemt distance, og regner det om til "rigtige" kilometer i timen.
Fremgangsmåde:
Opmål en strækning på din bane (f.eks. 2 meter).
Tag tid med et stopur på, hvor mange sekunder det tager toget at køre distancen.
Brug følgende formel:  
Hvor 3,6 er konverteringsfaktoren fra m/s til km/t, og 45 er din skala.
Eksempel:
Hvis dit tog i skala 1:45 bruger 5 sekunder på at køre 2 meter:  
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