# Gebruiksaanwijzing

### opladen / vervangen batterijen
Dit project gebruikt 2 x 18650 Li-ion batterijen met de bij behorende lader, wanneer u merkt dat de auto te wijnig kracht begint te geven om de motoren te laten draaien betekent dit dat de batterijen bijna leeg zijn, steek de lader in het stopcontact en steek de batterij in de lader deze zal rood schijnen als de batterij opgeladen is.

### draadloze communicatie
#### verbinding maken
Draadloze communicatie is jammer genoeg niet gelukt in dit project doordat de HC-05 module niet compatiebel is met een Iphone, hierdoor heb ik me gefocust op het rijden van de auto dan het mogelijk te maken via bluetooth te communiceren. Om te communiceren met de robot gebruiken we een kabel die verbinding maakt met de arduino leonardo en de pc.

#### commando's
debug [on/off]   
set cycle [µs]  
set power [0..255]  
set diff [0..1]  
set kp [0..]  
calibrate black  
calibrate white  

### kalibratie
De zwarte waardes worden gekalibreerd door de sensor te plaatsen boven het zwarte oppervlak voorzien op de baan. Type calibrate black in de seriële monitor en de zwarte waarden zouden tussen de -2 en +2 moeten liggen dit zou ideaal zijn als het niet zo zou zijn is het aan te raden om opnieuw te kalibreren. Hetzelfde geld voor de witwaarden te kalibreren juist moet je de sensor nu boven een wit oppervlak van de baan zetten en type je calibrate white in de seriële monitor. De waarden zouden tussen de 990 en 1000 moeten liggen.

### settings
De robot rijdt stabiel met volgende parameters:
Cycle 500
kp 12
power 200
diff 0,5
