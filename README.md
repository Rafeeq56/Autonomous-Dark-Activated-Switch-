#Autonomous-Dark-Activated-Switch-


#I've designed  and  constructed  an  autonomous  adjustable  dark-activated  switch  using electronic  components.  This  involves a  circuit  that  senses  changes  in  ambient light and controls the activation of a load (e.g., an AC light bulb) based on user-adjustable light intensity using a suitable potentiometer. 



#Code using Arduino IDE
const int lightSensorPin = A0;   // Analog pin connected to the light sensor
const int potentiometerPin = A1; // Analog pin connected to the potentiometer
const int relayPin = 7;          // Digital pin connected to the relay module

void setup() {
  pinMode(relayPin, OUTPUT);
  digitalWrite(relayPin, HIGH); // Turn off the relay initially

  Serial.begin(9600);
}

void loop() {
  int lightValue = analogRead(lightSensorPin);
  int threshold = analogRead(potentiometerPin);
  
  Serial.print("Light Value: ");
  Serial.println(lightValue);
  Serial.print("Threshold: ");
  Serial.println(threshold);

  if (lightValue < threshold) {
    digitalWrite(relayPin, LOW); // Turn on the relay and the connected load
  } else {
    digitalWrite(relayPin, HIGH); // Turn off the relay and the connected load
  }

  delay(1000); // Delay for stability
}

#Demonstration Video link
https://drive.google.com/drive/folders/1nAx-YE5WEbjnevwuerL698c_JJNA_jls?usp=sharing
