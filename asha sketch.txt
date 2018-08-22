const int trigpin = 6;
const int echopin = 5;
const int ledpin = 13;
long duration;
float distance;
void setup() 

{
 pinMode(trigpin,OUTPUT);
 pinMode(echopin,INPUT);
 pinMode(ledpin,OUTPUT);
 pinMode(A0,INPUT);
 pinMode(2,OUTPUT);
 pinMode(7,INPUT);
 Serial.begin(9600); 
}

void loop() 

{
  digitalWrite(trigpin,LOW);
  delay(200);

  digitalWrite(trigpin,HIGH);
  delay(100);
  digitalWrite(trigpin,LOW);
  duration = pulseIn(echopin,HIGH);

  distance = (duration/58.2);
  Serial.print("Distance:");
  Serial.println(distance);
  if(distance < 17.16)
  {
  digitalWrite(ledpin , HIGH);
  }
  else
  {
   digitalWrite(ledpin,LOW);
  }

  int lightresistance;
  lightresistance = analogRead(A0);
 Serial.println(“Resistance:”); 
 Serial.println(lightresistance);
  delay(1000);
  if(digitalRead(7)==HIGH && light>505)
  {
  digitalWrite(2,HIGH);
  delay(400);
  }
  else
  {
    digitalWrite(2,LOW);
  }

  
  }

