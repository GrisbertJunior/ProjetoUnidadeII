//Projeto I LED Piscando - Automação Residencial

int ledPin=10; // LED conectado na porta 10 do Arduino;
void setup() {
	pinMode(ledPin, OUTPUT); // Configura a porta como saida (OUTPUT); 
}
void loop() {
	digitalWrite(ledPin, HIGH); // Liga (HIGH) o LED; 
	delay(1000); // Espera um segundo; 
	
	digitalWrite(LedPin, LOW);  // Desliga (LOW) o LED; 
	delay(1000); // Espera um segundo; 
}