# Sensoren proof of concept

minimale hard- en software die aantoont dat minimaal 6 sensoren onafhankelijk van elkaar kunnen uitgelezen worden (geen calibratie, normalisatie of interpolatie). Hierbij moet een zo groot mogelijk bereik van de AD converter benut worden (indien van toepassing)

// Geef het aantal sensoren in de array aan
#define NUM_SENSORS 6

// Pinconfiguratie voor de sensoren
const int SENSOR_PINS[NUM_SENSORS] = {A0, A1, A2, A3, A4, A5};

void setup()
{
  Serial.begin(9600);
  delay(500);
}

void loop()
{
  unsigned int sensorValues[NUM_SENSORS];

  // Lees de sensoren
  readSensors(sensorValues);

  // Stuur de waarden naar de seriële monitor
  for (int i = 0; i < NUM_SENSORS; i++)
  {
    Serial.print("Sensor ");
    Serial.print(i);
    Serial.print(": ");
    Serial.print(sensorValues[i]);
    Serial.print("\t");
  }

  Serial.println(); // Nieuwe regel voor leesbaarheid

  delay(500);
}

void readSensors(unsigned int sensorValues[])
{
  for (int i = 0; i < NUM_SENSORS; i++)
  {
    sensorValues[i] = analogRead(SENSOR_PINS[i]);
  }
}
