#include <Servo.h> //The library is already included in Arduino.
#define servoPin 6 //define pin 6, servoPin as a variable.
#define potpin A1 //define analog pin A1, potpin as a variable.
Servo myservo; // creates a servo object to control a servo 
int val; //integer, use val as a variable
int Mval; //integer, use Mval as a variable
void setup() {
 Serial.begin(9600); //baud rate at 9600
 myservo.attach(servoPin); // use attach() method to specify the pin #
} 
void loop() {
 val = analogRead(potpin); // read the value from the potentiometer
 Mval = map(val, 0, 1023, 0, 180); // map the potentiometer value to the servo motor range (0 to 180 degrees)
 myservo.write(Mval); // set the servo position based on the mapped value
 Serial.print("Potentiometer: "); //print potentiometer in serial monitor
 Serial.print(val); //print val (value) in serial monitor
 Serial.print(" / Motor: "); //print / Motor: in serial monitor
 Serial.println(Mval); //Mval value will be in new line
 delay(100); // a 1 milliseconds delay to avoid rapid servo movement
}
