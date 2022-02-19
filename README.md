# Project1
Here will include all our videos, images, and process of completing the project. We began with our problem. Kyle wanted to be notified whenever his front door detached motion. To do this we needed a SIM 900A (or any other) GSM Module with SIM inserted which sends text messages and calls, however we did not have access to this GSM module, so we opted for a I2C LCD which just displays messages. Then we needed to find a sensor. We tried a PIR sensor, but it was not working properly so we switched our sensor to an ultrasonic sensor. With the ultrasonic sensor we could tell the distance of an object and therefore could code when the LCD could turn on. We only wanted it when someone was close to the sensor to send a message to whoever was opening the door. However, if we were to code it for our original issue, the distance of detection would be larger as to notify the homeowner for any movement outside. Our final project is a working prototype that displays a message “Welcome home” when an object is detached within 50 inches of the sensor, just enough to be triggered when the door is opened right in front of it.

//project code

#include <Wire.h>

#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x3F,16,2);

#define echoPin 2 // attach pin D12 Arduino to pin Echo of HC-SR04
#define trigPin 3 //attach pin D13 Arduino to pin Trig of HC-SR04

// defines variables
long duration; // variable for the duration of sound wave travel
int distance_cm; // variable for centimeters measurement
int distance_inch; // variable for inches measurement
void setup() {
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an OUTPUT
  pinMode(echoPin, INPUT); // Sets the echoPin as an INPUT
  Serial.begin(9600); // // Serial Communication is starting with 9600 of baudrate speed
  Serial.println("Ultrasonic Sensor HC-SR04 Test"); // print some text in Serial Monitor
  Serial.println("with Arduino UNO R3");
  lcd.init()
  lcd.clear();
  lcd.backlight();
}

void loop() {
  // Clears the trigPin condition
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  // Sets the trigPin HIGH (ACTIVE) for 10 microseconds
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  // Reads the echoPin, returns the sound wave travel time in microseconds
  duration = pulseIn(echoPin, HIGH);
  // Calculating the distance
  distance_cm = duration * 0.034 / 2; // Speed of sound wave divided by 2 (go and back)
  distance_inch = duration * 0.0133 / 2; // Speed of sound wave divided by 2 (go and back)
  // Displays the distance on the Serial Monitor
  if (distance_inch < 50){
    lcd.setCursor(0, 0);
    lcd.print("Welcome Home");
    //lcd.print(distance_cm);
    //lcd.println(" cm  ");
    lcd.setCursor(0, 1);
    lcd.print("Distance: ");
    lcd.print(distance_inch);
    lcd.println(" inch");
  }else{
    lcd.setCursor(0, 0);
    lcd.print("                ");
    lcd.setCursor(0, 1);
    lcd.print("                ");
  }
}
