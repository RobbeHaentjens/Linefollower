# Instructable

Een instructable is een stappenplan - zonder verdere uitleg - hoe je vertrekkend van de bill of materials en gebruik makend van de technische tekeningen de robot kan nabouwen. Ook de nodige stappen om de microcontroller te compileren en te uploaden staan beschreven.  

### stap 1
bestel alle componenten uit de bill of materials  

### stap 2

Begin met het vastmaken van de arduino op de plexi plaat, dit doen we op de voorkant van de plexiplaat waar de sensor vooraan plaats vindt. Het kleine breadboardje zetten we net achter de arduino. De batterijhouder plaatsen we helemaal achteraan. de H-brug plaatsen we op het breadboard. De wielen moeten zo divht mogelijk tegen de sensor maar dit kan niet door het gewicht van de batterijhouder zorg er dus voor dat je het evenwichtspunt zoekt en de motoren net daar plaatst voor maximale efficiëntie. 

### stap 3

Volg het aansluitschema voor het bedraden van alle componenten.

### stap 4

Nu uploaden we de finale code naar de arduino, kalibreer de zwarte waardes en de witte waardes door in de seriële monitor calibrate black in te typen wanneer de sensor boven het zwarte oppervlak van de baan staat. Doe dan hetzelfde voor calibrate white bij een wit stuk van de baan. 

### stap 5

U kunt uw auto nu op de baan plaatsen en de waarden kp power en diff beginnen aanpassen door set kp, set power en set diff te typen in de seriële monitor. 
het is aan te raden om kp intestellen  tussen 0 en 50
power tussen 0 en 255
diff tusesen 0 en 1
Probeer eens kp 10 power 100 en diff 0,5 upload dit naar de arduino en haal de kabel er uit nu zou de robot de lijn al moeten volgen je kan met de waarden spelen om zo een optimaal mogelijke auto te maken.

