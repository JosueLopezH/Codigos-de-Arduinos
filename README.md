# Codigos-de-Arduinos
Implementación de los códigos de las prácticas vistas en clases

---------Codigo para prender pantalla LCD------------
#include <LiquidCrystal.h>

int ldr = A5;
const int ledazul = 10;
int valor;
int dt = 1000;


LiquidCrystal lcd(7,6,5,4,3,2);

void setup(){
    Serial.begin(9600);
    pinMode(ldr, INPUT);
    pinMode(ledazul, OUTPUT);

    lcd.begin(16,2);
    
  
}
 void loop(){

  int valor = analogRead(ldr);
  Serial.println(valor);
  delay(dt);

  lcd.setCursor(2,0);
  lcd.print(valor);
  delay(500);
  

 
  

  if(valor>700){
    digitalWrite(ledazul, HIGH);
 
  }
  if(valor<700){
    digitalWrite(ledazul, LOW);
 
  }
 }
--------------Codigo para semaforo con leds---------------
int verde = 13;
int amarillo = 12;
int rojo = 11;

void setup() {

  pinMode(verde, OUTPUT);
  pinMode(amarillo, OUTPUT);
  pinMode(rojo, OUTPUT);

  
}

void loop() {
  // Enciende el LED
  digitalWrite(verde, HIGH);
  // Espera 1 segundo (1000 milisegundos)
  delay(25);
  
   digitalWrite(amarillo, HIGH);
  // Espera 1 segundo (1000 milisegundos)
  delay(25);

 
  digitalWrite(rojo, HIGH);
  // Espera 1 segundo (1000 milisegundos)
  delay(25);


  
  // Apaga el LED
  digitalWrite(verde, LOW);
  // Espera 1 segundo
  delay(67);
  
  // Apaga el LED
  digitalWrite(amarillo, LOW);
  // Espera 1 segundo
  delay(25);

   // Apaga el LED
  digitalWrite(rojo, LOW);
  // Espera 1 segundo
  delay(25);
}

---------Codigo Serie de Navidad----------------------
int led1 = 13;
int led2 = 12;
int led3 = 11;
int led4 = 10;
int led5 = 9;

void setup() {
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);
  pinMode(led4, OUTPUT);
  pinMode(led5, OUTPUT);
  
}

void loop() {
  
  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(500);   
  
  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(500);
  
  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, HIGH);
  delay(500);
  
  digitalWrite(led1, LOW);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(500);


  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, HIGH);
  digitalWrite(led5, LOW);
  delay(500);    

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, HIGH);
  delay(400);

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, HIGH);
  digitalWrite(led5, LOW);
  delay(400);

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(400);

  digitalWrite(led1, LOW);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(400);

  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(400); 

    digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, HIGH);
  delay(300);

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, HIGH);
  digitalWrite(led5, LOW);
  delay(300);

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(300);

  digitalWrite(led1, LOW);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(300);

  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(300); 

      digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, HIGH);
  delay(300);

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, HIGH);
  digitalWrite(led5, LOW);
  delay(200);

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(200);

  digitalWrite(led1, LOW);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(200);

  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
  delay(200); 
}

----------Codigo para fotoResistencia-------------
int ldr = A5;
int valor;
int dt = 1000;

void setup() {
  Serial.begin(9600);
  pinMode(ldr,INPUT);
  

}

void loop() {
  int valor = analogRead(ldr);
  Serial.println(valor);
  delay(dt);
  
  digitalWrite(led3, HIGH);
  delay(dt);

  
}

---------Codigo para sensor UltraSonico------------
//Variables declaradas
int trig = 10;
int eco = 9;
int led = 3;
int duracion;
int distancia;

void setup() {
  pinMode (trig, OUTPUT);
  pinMode (eco, INPUT);
  pinMode (led, OUTPUT);
  Serial.begin (9600);
}

void loop() {
  digitalWrite (trig, HIGH);
  delay(1);
  digitalWrite (trig, LOW);
  duracion = pulseIn (eco, HIGH);
  distancia = duracion / 58.2;
  Serial.print(distancia);
  Serial.print ("centimetros");
  Serial.println ();

  delay(200);
 

}

--------Codigo de fotoResistencia 2da parte Semaforo de proximidad---------
int trig =10;
int eco= 9;
int led1 = 2;
int led2 = 3;
int led3 = 4;
int led4 = 5;
int led5 = 6;
int duracion;
int distancia;

void setup(){
  
  pinMode(trig, OUTPUT);
  pinMode(eco, INPUT);
  pinMode(led1, OUTPUT);
  Serial.begin (9600); 
  }

  void loop(){
    
    digitalWrite(trig, HIGH);
    delay(1);
    digitalWrite(trig, LOW);
   
    duracion = pulseIn(eco, HIGH);
    distancia = duracion/58.2;
    Serial.print(distancia);
    Serial.print(" Centimetros");
    Serial.println();

    delay(200);


    if (distancia <= 30){
      digitalWrite(led1, HIGH);
      delay(100);
      
      }
       if (distancia <= 25){
      digitalWrite(led2, HIGH);
      delay(100);
      
      }
       if (distancia <= 20){
      digitalWrite(led3, HIGH);
      delay(100);
      
      }
       if (distancia <= 15){
      digitalWrite(led4, HIGH);
      delay(100);
      
      }
       if (distancia <= 10){
      digitalWrite(led5, HIGH);
      delay(100);
      
      }
     
      else{
        digitalWrite(led1,LOW);
        digitalWrite(led2,LOW);
        digitalWrite(led3,LOW);
        digitalWrite(led4,LOW);
        digitalWrite(led5,LOW);
        delay(100);
        
        }
        
      
 }

---------Codigo para sensor de Temperatura/Humedad---------
#include <DHT.h>
#include <DHT_U.h>
 int led =2;
 int SENSOR = 3;
 int temperatura;
 int humedad;

 DHT dht(SENSOR, DHT11);

void setup() {
  Serial.begin(9600);
  dht.begin();
  pinMode(led, OUTPUT);

}

void loop() {
 temperatura = dht.readTemperature();
 humedad = dht.readHumidity();
 delay(1);
 Serial.print("Temperatura ");
 Serial.print(temperatura);
 Serial.print(" Humedad ");
 Serial.println(humedad);
 delay(500);

 if (temperatura >=28){
  
  digitalWrite(led,HIGH);
  }
 

}

---------Codigo para Led RGB--------------
int rojo=10;
int azul = 11;
int verde=12;

String cadena;
void setup(){
  
 pinMode(rojo, OUTPUT);
 pinMode(azul, OUTPUT);
 pinMode(verde, OUTPUT);
}
void loop (){
analogWrite(rojo,25);
analogWrite(azul,32);
analogWrite(verde,19);
}

