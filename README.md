# Analog Voltage reading with Serial Monitor
Using the Arduino to measure analog voltage with the serial monitor.

### Tools
* Arduino board
* breadBoard
* Jumper wires
* Potentiometer
* Led

### Circuit layout
![Screenshot 2022-08-19 083640](https://user-images.githubusercontent.com/109004035/185551780-de49e6a2-a5ce-49d0-99c7-692061d0d63d.jpg)

### The Code

```
int readPin=A3;
int readVal;
float V2=0;
int delayTime=500;

void setup() {
  // put your setup code here, to run once:
pinMode(readPin,INPUT);
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
readVal=analogRead(readPin);
V2=readVal*(5./1023.);
Serial.println(V2);
delay(delayTime);
}
```

### How to use

For this circuit, i have used the potentiometer for testing and demonstration of the readings, however, _you can use this code and unplug the A3 pin from the potentiometer and connect it to other circuit where you would like to measure the voltage._

**the Arduino readings are 0-1023 ( 2^10 , or 10-Bit)**, so in the code, I had to translate the scale to up to 5 (since Arduino supplies 5v), else, scale is adjustable.

For the simulation in Tinkercad, you can open the serial monitor to check the readings, and I have used an LED also as a way for demonstrating voltage changes!

![Screenshot 2022-08-19 083736](https://user-images.githubusercontent.com/109004035/185552777-8e415e41-27c7-4527-a692-f5c886f4417a.jpg)

