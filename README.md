//Projeto II Código Morse S.O.S - Automação Residencial

int ledPin = 10;  

void setup() 
{
pinMode(ledPin, OUTPUT); 
}

void loop() 
{

// 3 dits;
for (int x=0; x<3; x++) { 
	digitalWrite(ledPin, HIGH); 
delay(150); // espera 150ms
	digitalWrite(ledPin, LOW); 
delay(100); 
}

delay(100); 
