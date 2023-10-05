# start/stop interrupt proof of concept
minimale hard- en software die de correcte werking van een start/stop drukknop aantoont, gebruik makend van een hardware interrupt

const int buttonPin = 2;  // Pin waarop de drukknop is aangesloten
volatile bool buttonState = LOW;  // Variabele om de toestand van de drukknop bij te houden

void setup() {
  pinMode(buttonPin, INPUT);  // Zet de pin van de drukknop als input
  attachInterrupt(digitalPinToInterrupt(buttonPin), buttonISR, CHANGE);  // Configureer een interrupt op de drukknop-pin
  Serial.begin(9600);  // Start de seriële communicatie voor debugging (optioneel)
}

void loop() {
  // Je hoofdprogramma kan hier verder gaan
  // Omdat de interrupt de toestand van de drukknop bijhoudt, kun je deze variabele gebruiken waar nodig in je code
}

void buttonISR() {
  buttonState = digitalRead(buttonPin);  // Lees de toestand van de drukknop
  Serial.print("Drukknop ingedrukt: ");
  Serial.println(buttonState);
}
