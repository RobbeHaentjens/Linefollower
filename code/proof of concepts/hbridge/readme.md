# H-Bridge proof of concept

// Pinconfiguratie voor de H-brug DRV8833
const int STBY = 8;
const int motor1PWM1 = 9;  // PWM-pin1 voor motor 1
const int motor1PWM2 = 10; // PWM-pin2 voor motor 1


const int motor2PWM1 = 11;  // PWM-pin1 voor motor 2
const int motor2PWM2 = 13; // PWM-pin2 voor motor 2

void setup() {
  // Initialisatie van de pinnen
  pinMode(motor1PWM1, OUTPUT);
  pinMode(motor1PWM2, OUTPUT);

  pinMode(motor2PWM1, OUTPUT);
  pinMode(motor2PWM2, OUTPUT);
  pinMode(STBY, OUTPUT);
}

void loop() {
  
  // Vooruit draaien, motor 1
  digitalWrite(STBY, HIGH);


  delay(1000);
for (int i = 0; i <= 255; i++) {
    // Doe hier iets met de variabele 'i'
    // Bijvoorbeeld, print de waarde naar de seriële monitor
    Serial.begin(9600);
    // Achteruit draaien, motor 1
  analogWrite(motor1PWM1, i);
    // Achteruit draaien, motor 2
  analogWrite(motor2PWM1, i);

    // Plaats hier een vertraging om de snelheid van de lus te beheersen
    delay(20);
  }

  
  delay(2000);

  for (int ii = 255; ii >= 0; ii--) {
    // Doe hier iets met de variabele 'i'
    // Bijvoorbeeld, print de waarde naar de seriële monitor
    Serial.begin(9600);
    // Achteruit draaien, motor 1
  analogWrite(motor1PWM1, ii);
    // Achteruit draaien, motor 2
  analogWrite(motor2PWM1, ii);

    // Plaats hier een vertraging om de snelheid van de lus te beheersen
    delay(20);
  }

  
  delay(2000);

  for (int iii = 0; iii <= 255; iii++) {
    // Doe hier iets met de variabele 'i'
    // Bijvoorbeeld, print de waarde naar de seriële monitor
    Serial.begin(9600);
    // Achteruit draaien, motor 1
  analogWrite(motor1PWM2, iii);
  analogWrite(motor2PWM2, iii);

    // Plaats hier een vertraging om de snelheid van de lus te beheersen
    delay(20);
  }

  
  delay(2000);

  for (int iiii = 255; iiii >= 0; iiii--) {
    // Doe hier iets met de variabele 'i'
    // Bijvoorbeeld, print de waarde naar de seriële monitor
    Serial.begin(9600);

    // Achteruit draaien, motor 2
  analogWrite(motor1PWM2, iiii);
  analogWrite(motor2PWM2, iiii);
    // Plaats hier een vertraging om de snelheid van de lus te beheersen
    delay(20);
  }

  
  delay(2000);
}
