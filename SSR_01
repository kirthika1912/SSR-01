#include<Servo.h>
Servo s;
int tr=2;
int e=3;
void setup()
{
  s.attach(5);
  pinMode(4,INPUT);
  pinMode(12,OUTPUT);
  pinMode(13,OUTPUT);
  pinMode(tr,OUTPUT);
  pinMode(e,INPUT);
  Serial.begin(9600);
}

void loop()
{
  double a = analogRead(A0);
  double t = (((a/1024)*5)-0.5)*100;
  if(t>100)
  { 
    Serial.println("FIRE ALARM!!!");
   {
     for(int i=0; i<30000; i++)
       tone(12,i);
     digitalWrite(13,1);
     delay(1000);
     digitalWrite(13,0);
     delay(1000);
   }
  int b = digitalRead(4);
  if(b==1)
  {
    {
      Serial.println("MOTION DETECTED!");
      
      
    }
    digitalWrite(tr,0);
    digitalWrite(tr,1);
    delayMicroseconds(10);
    digitalWrite(tr,0);
    float dur = pulseIn(e,HIGH);
    float dis = (dur*0.0343)/2;
    Serial.print("Distance in cm is ");
    Serial.println(dis);
    
    
    if(dis<320)
    {
        for(int i=0;i<=180;i++)
          {
            s.write(i);
            delay(10);
          }
        for(int i=180;i>=0;i--)
          {
            s.write(i);
            delay(10);
          }
        Serial.println("DOOR OPENED...");
    }
  }

  }  
  else if(t<100)
  {
    noTone(12);
    Serial.println("HAPPY HOME:)");
  }
}
