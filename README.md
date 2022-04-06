
#include <Adafruit_DHT.h>
DHT dht(A0, DHT11);

int led = D7; //LED on board

void setup() {
    
    
  pinMode(led, OUTPUT);

  dht.begin();

}

void loop() {
    
      digitalWrite(led, HIGH);   // Turn ON the LED

 

      float temp = dht.getTempCelcius(); //read temperature as celcius       

      Particle.publish("temp", String(temp), PRIVATE);

      digitalWrite(led, LOW);    // Turn OFF the LED

  delay(30000);               // Wait for 30 seconds

}
