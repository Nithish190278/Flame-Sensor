int ledpin=13;
int led2=12; 
int flamepin=A4;
 int buzpin=11;
 int threshold=200;
int flamesensvalue=0; 
void setup() {
Serial.begin(9600);
pinMode(ledpin,OUTPUT);
pinMode(led2,OUTPUT);
pinMode(flamepin,INPUT);
pinMode(buzpin,OUTPUT);
}
void loop() {
flamesensvalue=analogRead(flamepin); 
if (flamesensvalue<=threshold) { 
digitalWrite(ledpin,HIGH); 
tone(buzpin,10000);
delay(1000); 
}
else{
digitalWrite(led2,HIGH); 
digitalWrite(ledpin,LOW);
noTone(buzpin);
digitalWrite(led2,LOW);
}
 }
