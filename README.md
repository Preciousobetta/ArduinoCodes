  //////////////////////////////////////////////
  //        HALL EFFECT SENSOR DEMO           //
 //          Author: Obetta Precious           //
/////////////////////////////////////////////

// Pin Definion
int ledPin = 5;
int hallSensorPin = A0; 


void setup() {
  Serial.begin (9600); 

  // pin setup mode
  pinMode(ledPin, OUTPUT);
  pinMode(hallSensorPin, INPUT);

}

void loop() {
  // Read raw analog value
 int sensorValue = analogRead(A0);

// map range
 int mappedValue = map(sensorValue, 0, 1023, 0,1023);

// Check threshood
 if (mappedValue > 900) {
  tone(ledPin, 1000);
  delay(1000);

  // Serial.println("the state is low");
 }

 else {
  noTone(ledPin);

  //  Serial.println("the state is high");
 }
  // Serial.println("hallsensorPin: ");
  
  Serial.print("Analog reading = "); 
  Serial.println(sensorValue);

  delay(100);

}
