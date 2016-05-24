//Projeto I LED Piscando - Automa��o Residencial
  
 
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


//Projeto II C�digo Morse S.O.S - Automa��o Residencial

int ledPin = 10;  // LED conectado na porta 10 do Arduino;


void setup() // Inicializa��o do Arduino
{
pinMode(ledPin, OUTPUT); // Configura pino do LED como sa�da;
}

void loop() // Loop principal do programa;
{
// 3 dits
for (int x=0; x<3; x++) {
digitalWrite(ledPin, HIGH); // Acende o LED;
delay(150); // espera 150ms
digitalWrite(ledPin, LOW); // Apaga o LED;
delay(100); // espera 100ms
}

delay(100); // Delay de 100ms para ter um gap entre as letras;

// 3 dahs
for (int x=0; x<3; x++) {
digitalWrite(ledPin, HIGH); // Acende o LED;
delay(400); // espera 400ms
digitalWrite(ledPin, LOW); // Apaga o LED;
delay(100); // espera 100ms
}


delay(100); // Delay de 100ms para ter um gap entre as letras;

// 3 dits novamente
for (int x=0; x<3; x++) {
digitalWrite(ledPin, HIGH); // Acende o LED;
delay(150); // espera 150ms
digitalWrite(ledPin, LOW); // Apaga o LED;
delay(100); // Espera 100ms;
}

delay(5000); // Espera 5 segundos antes de repetir o c�digo de SOS;
}

//Projeto III Sinal Ingles - Automa��o Residencial

int ledDelay = 7000; // Espera SETE SEGUNDOS entre o LED Red e o LED Green;
int redPin = 10; // LED Red conectado na porta 10 do Arduino;
int yellowPin = 9; // LED Yellow conectado na porta 9 do Arduino;
int greenPin = 8; // LED Green na porta 8 do Arduino;

void setup() {
	pinMode(redPin, OUTPUT); // Configura pino do LED Red como sa�da;
	pinMode(yellowPin, OUTPUT); // Configura pino do LED Yellow como sa�da;
	pinMode(greenPin, OUTPUT);	// Configura pino do LED Green como sa�da;	
}	

void loop(){
	digitalWrite(redPin, HIGH); // Acende o LED Red;
	delay(ledDelay); //Espera 7000ms (7 segundos);
	
	digitalWrite(yellowPin, HIGH); // Acende o LED Yellow;
	delay(2000); //Espera 2000ms (2 segundos)
	
	digitalWrite(greenPin, HIGH); // Acende o LED Green;
	delay(ledDelay); // Espera 7000ms(7 segundos);
	
	digitalWrite(redPin, LOW); // Apaga o LED red;
	digitalWrite(yellowPin, LOW); // Apaga o LED yellow;
	delay(ledDelay); // Espera 7000ms (7 segundos);
	
	digitalWrite(yellowPin, HIGH); // Acende o LED Yellow;
	digitalWrite(GreenPin, HIGH); // Acende o LED Green;
	delay(2000); 
	
	digitalWrite(yellowPin, HIGH);
	
	}
	
//Projeto IV Ilumina��o Sequencial - Automa��o Residencial

byte ledPin[] = {4, 5, 6, 7, 8, 9, 10, 11, 12, 13}; 
 int ledDelay(65);                     
 int direction = 1;  
 int currentLED = 0;  
 unsigned long changeTime;  
   
 void setup(){  
  for (int x=4; x<14; x++) {                
   pinMode(ledPin[x], OUTPUT);   
  }  
  changeTime = millis();  
 }  
   
 void loop() {  
  if ((millis() - changeTime) > ledDelay) {    
   changeLED();                       
   changeTime = millis();  
  }  
 }  