# H-Bridge proof of concept

minimale hard- & software die aantoont dat 2 motoren onafhankelijk van elkaar kunnen draaien, en (traploos) regelbaar zijn in snelheid en draairichting.

#include <Wire.h>
#include <Adafruit_MotorShield.h>
#include "utility/Adafruit_MS_PWMServoDriver.h"

// Maak een Adafruit Motor Shield-object met de I2C-adres van DRV8833 (standaardadres)
Adafruit_MS_PWMServoDriver pwm = Adafruit_MS_PWMServoDriver(0x60);

// Definieer de pinnen voor Motor 1
uint8_t pwmPinMotor1 = 9;   // PWM-pin voor Motor 1 (PWMA)
uint8_t ain1PinMotor1 = 2;  // Ain1-pin voor Motor 1
uint8_t ain2PinMotor1 = 3;  // Ain2-pin voor Motor 1

// Definieer de pinnen voor Motor 2
uint8_t pwmPinMotor2 = 10;  // PWM-pin voor Motor 2 (PWMB)
uint8_t bin1PinMotor2 = 4;  // Bin1-pin voor Motor 2
uint8_t bin2PinMotor2 = 5;  // Bin2-pin voor Motor 2

void setup() {
  // Initialiseer de Adafruit Motor Shield
  pwm.begin();
  pwm.setPWMFreq(1600);  // PWM-frequentie instellen op 1.6 kHz (standaard)
  
  // Motor 1 vooruit met 50% snelheid
  motorForward(pwmPinMotor1, ain1PinMotor1, ain2PinMotor1, 2048); // 2048 is de helft van het PWM-bereik (4096)
  delay(2000);  // Wacht 2 seconden
  
  // Motor 2 achteruit met 75% snelheid
  motorBackward(pwmPinMotor2, bin1PinMotor2, bin2PinMotor2, 3072); // 3072 is 75% van het PWM-bereik
  delay(2000);  // Wacht 2 seconden
  
  // Stop Motor 1
  motorStop(pwmPinMotor1, ain1PinMotor1, ain2PinMotor1);
  delay(1000);  // Wacht 1 seconde
  
  // Stop Motor 2
  motorStop(pwmPinMotor2, bin1PinMotor2, bin2PinMotor2);
}

void motorForward(uint8_t pwmPin, uint8_t ain1Pin, uint8_t ain2Pin, uint16_t speed) {
  pwm.setPWM(pwmPin, 0, speed);
  digitalWrite(ain1Pin, HIGH);
  digitalWrite(ain2Pin, LOW);
}

void motorBackward(uint8_t pwmPin, uint8_t bin1Pin, uint8_t bin2Pin, uint16_t speed) {
  pwm.setPWM(pwmPin, 0, speed);
  digitalWrite(bin1Pin, HIGH);
  digitalWrite(bin2Pin, LOW);
}

void motorStop(uint8_t pwmPin, uint8_t inPin1, uint8_t inPin2) {
  pwm.setPWM(pwmPin, 0, 0);
  digitalWrite(inPin1, LOW);
  digitalWrite(inPin2, LOW);
}

void loop() {
  // Je kunt hier je eigen logica toevoegen
}
