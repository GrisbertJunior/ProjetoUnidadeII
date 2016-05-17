//Projeto I LED Piscando - Automação Residencial

int ledPin=10; 
void setup() {
	pinMode(ledPin, OUTPUT);
}
void loop() {
	digitalWrite(ledPin, HIGH);
	delay(1000);
	digitalWrite(LedPin, LOW);
	delay(1000);
}