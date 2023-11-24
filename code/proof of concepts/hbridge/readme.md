# H-Bridge proof of concept

void loop() {
  
  // Vooruit draaien, motor 1
  digitalWrite(STBY, HIGH);
  analogWrite(motor1PWM1, 150); // Traploze snelheid, waarde tussen 0 en 255

  delay(2000); // Wacht 2 seconden


  // Stop motor 1
  analogWrite(motor1PWM1, 0);

  delay(1000);

  // Vooruit draaien, motor 2
  analogWrite(motor2PWM1, 100);

  delay(2000);



  // Stop motor 2
  analogWrite(motor2PWM1, 0);

  delay(1000);
  // Achteruit draaien, motor 1
  analogWrite(motor1PWM1, 255);
    // Achteruit draaien, motor 2
  analogWrite(motor2PWM1, 255);


  delay(2000);

    // Achteruit draaien, motor 1
  analogWrite(motor1PWM1, 100);
    // Achteruit draaien, motor 2
  analogWrite(motor2PWM1, 100);


  delay(2000);
}
