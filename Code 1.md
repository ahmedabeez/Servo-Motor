# Servo-Motor
//Develop the program which would generate a sweep motion (0°-180° and then 
180°-0°) by using a servo motor.

#include <Servo.h> //library is already in the Arduino 
#define servoPin 6 //define pin 6 by use of servoPin as a variable
Servo myservo; // creates servo object to control a servo
int pos; // pos as a variable to store the servo position
void setup() { 
 Serial.begin(9600); //baud rate at 9600
 myservo.attach(servoPin); // use attach() method to specify the pin #
}
void loop() { 
 // Sweep from 0 to 180 degrees
 for (pos = 0; pos <= 180; pos++) {
 myservo.write(pos); //get run acc. to for loop (pos value)
 Serial.println(pos); //new line for pos
 delay(100); delay for 1 milliseconds
 }
 // Sweep back from 180 to 0 degrees
 for (pos = 180; pos >= 0; pos--) { 
 myservo.write(pos); //get run acc. to for loop (pos value)
 Serial.println(pos); //new line for pos
 delay(100); delay for 1 milliseconds
 }
}
