# 3led

Project Title:
Control 3 LEDs with 3 Pushbuttons using Arduino UNO (Tinkercad Simulation)
Objective:
The objective of this project is to simulate a simple input-output control system using Arduino UNO, where three LEDs are controlled by three corresponding pushbuttons. When a button is pressed, its associated LED turns ON; when released, the LED turns OFF.
Tools & Components Used:
Tinkercad Circuits
Arduino UNO
Breadboard (Full-size)
3 x LEDs (Red)
3 x Pushbuttons
3 x 220Ω Resistors (for LEDs)
3 x 10kΩ Resistors (pull-down for buttons)
Jumper Wires
USB Cable (Virtual, for Arduino power)
Circuit Description:
LEDs:
Each LED is connected in series with a 220Ω resistor to limit current.
The cathode (short leg) of each LED is connected to GND (ground).
The anode (long leg) is connected to a digital pin on the Arduino through the resistor.
Pushbuttons:
Each pushbutton is connected between 5V and a digital input pin.
A 10kΩ pull-down resistor is connected between each button’s input side and GND to ensure a default LOW signal when the button is not pressed.
When a button is pressed, the input pin receives HIGH (5V), turning on the respective LED.
Pin Connections:
Component	Arduino Pin	Purpose
LED 1 (Top)	D2	Output to LED 1
LED 2 (Middle)	D3	Output to LED 2
LED 3 (Bottom)	D4	Output to LED 3
Button 1	D5	Input from Button 1
Button 2	D6	Input from Button 2
Button 3	D7	Input from Button 3
Working Logic:
Default State: All LEDs are OFF.
When a button is pressed:
The corresponding digital input pin reads HIGH → Arduino sends HIGH signal to the respective LED pin → LED turns ON.
When the button is released:
Input pin reads LOW → Arduino sends LOW signal to LED → LED turns OFF.
Conclusion:
This Tinkercad simulation demonstrates a basic but essential concept in electronics: digital input and output control using Arduino. This forms the foundation for more complex interactive systems such as security panels, games, or user interfaces.


Code:
//Buttons
const int buttonPin1= 2;  
const int buttonPin2= 3;
const int buttonPin3 = 4; 
const int ledPin = 13;    
int buttonState = 0;  
void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin1, INPUT);
    pinMode(buttonPin2, INPUT);
  pinMode(buttonPin3, INPUT);
}
void loop() {
 int buttonState1 = digitalRead(buttonPin1);
  int buttonState2 = digitalRead(buttonPin2);
  int buttonState3 = digitalRead(buttonPin3);
  if (buttonState == HIGH) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
}
