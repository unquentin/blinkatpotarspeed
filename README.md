# blinkatpotarspeed
ARDUINO - a LED blinks at a speed based on a potentiometer value


/*
  AnalogReadSerial
  Reads an analog input on pin 0, prints the result to the serial monitor.
  Attach the center pin of a potentiometer to pin A0, and the outside pins to +5V and ground.
 
 This example code is in the public domain.
 */
int led = 13;
int timing = 0;

// the setup routine runs once when you press reset:
void setup() {
  pinMode(led, OUTPUT);   
  // initialize serial communication at 9600 bits per second:
  Serial.begin(9600);
}

// the loop routine runs over and over again forever:
void loop() {
  // read the input on analog pin 0:
  int sensorValue = analogRead(A0);
  // print out the value you read:
  Serial.println(sensorValue);
  digitalWrite(led, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(sensorValue);               // wait for a second
  digitalWrite(led, LOW);    // turn the LED off by making the voltage LOW
  delay(sensorValue);               // wait for a second
  delay(1);        // delay in between reads for stability
}
