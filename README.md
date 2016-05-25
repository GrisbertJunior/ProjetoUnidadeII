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

byte ledPin[] = {4, 5, 6, 7, 8, 9, 10, 11, 12, 13};       // Cria um array para os pinos dos LEDs; 
 int ledDelay(65);        // Intervalo entre as altera��es;              
 int direction = 1;  
 int currentLED = 0;  
 unsigned long changeTime;  
   
 void setup(){  
  for (int x=13; x<13; x++) {      // Define todos os pinos como sa�da;            
   pinMode(ledPin[x], OUTPUT);   
  }  
  changeTime = millis();  
 }  
   
 void loop() {  
  if ((millis() - changeTime) > ledDelay) {    // Verifica se j� transcorreram ledDelay;
   changeLED();    // Ms desde a �ltima altera��o                     
   changeTime = millis();  
  }  
 }  
 
 void changeLED() {  
  for (int x=4; x<14; x++) {       // Apaga todos os LEDs;  
   digitalWrite(ledPin[x], LOW);  
  }  
  digitalWrite(ledPin[currentLED], HIGH);       // Acende o LED atual; 
  currentLED += direction;         // Incrementa de acordo com o valor de direction;  
  
  // Altera a dire��o se tivermos atingido o fim ; 
  if (currentLED == 13) {direction = -1;}  
  if (currentLED == 4) {direction = 1;}  
 }  
 
 //Projeto V Pressionando botao para ligar o LED - Automa��o Residencial;
   
 int ledPin = 8;  
 int button = 3; // Bot�o;  
   
 void setup(){  
  pinMode(ledPin, OUTPUT); // Inicializa o pino de sa�da do arduino;  
  pinMode(button, INPUT); // Inicializa o pino entrara para receber sinal;  
 }  
 
 void loop(){  
  int state = digitalRead(button); // Recebe sinal do bot�o;  
    
  if(state == HIGH){ // Se o bot�o estiver precionado liga o LED;  
   digitalWrite(ledPin, HIGH);  
  }  
  else{       // Sen�o o LED apaga;  
   digitalWrite(ledPin, LOW);  
  }  
 }  
 
 
 //Projeto VI Usando LCD - Automa��o Residencial;
 
 
  #include <LiquidCrystal.h> //Inclui a biblioteca do LCD; 
    
 LiquidCrystal lcd(12, 11, 5, 4, 3, 2); //Configura os pinos do Arduino para se comunicar com o LCD;  
    
 int temp=0; // Utilizado para escrever no LCD, vai 0 - 9 e depois zera;  
 int cont=0; // Depois que o temp passa do 9 o cont incrementa;  
   
 void setup(){  
  lcd.begin(16, 2);        //Inicia o LCD com dimens�es 16x2(Colunas x Linhas);  
  lcd.setCursor(0, 0); //Posiciona o cursor na primeira coluna(0) e na primeira linha(0) do LCD;  
  lcd.print("Bem vindo!");  
  lcd.setCursor(0, 1); //Posiciona o cursor na primeira coluna(0) e na segunda linha(1) do LCD;  
  lcd.print("Grupo ARmix");  
   
  lcd.setCursor(14, 0);  
  lcd.print(cont);  
 }