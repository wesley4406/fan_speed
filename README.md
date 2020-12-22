# fan_speed
控制




***
int a = -1;  
boolean SW = true;  
void setup()  
{  
Serial.begin(9600);  
pinMode(2,OUTPUT);  
pinMode(5,OUTPUT);  
pinMode(6,OUTPUT);   
pinMode(4,INPUT);  
pinMode(8,OUTPUT);  
pinMode(9,OUTPUT);  
pinMode(10,OUTPUT);  
pinMode(11,OUTPUT);  
pinMode(12,OUTPUT);  
pinMode(13,OUTPUT);  
pinMode(3,INPUT);  
}  
  
void loop()  
{  
if (digitalRead(3) == 0)  
{  
Serial.print("Button: ");  
Serial.println(digitalRead(3));  
while(digitalRead(3) == 0);  
if (SW == true)  
{  
SW = false;  
a=-1;  
digitalWrite(13,HIGH);  
digitalWrite(12,HIGH);  
digitalWrite(11,HIGH);  
digitalWrite(10,HIGH);  
digitalWrite(9,HIGH);  
digitalWrite(8,HIGH);  
}  
else  
{  
SW = true ;  
a = 0;  
}  
Serial.print("SW: ");  
Serial.println(SW);  
delay(250);  
}  
if (digitalRead(4) == 0)  
{  
while(digitalRead(4) == 0);  
if( SW == true )  
{  
a = (a+1)%6;  
delay(250);  
Serial.print("Speed: ");  
Serial.println(a);  
}  
}  
switch(a)  
{  
case 0:  
Speed(110);  
digitalWrite(13,LOW);  
digitalWrite(12,HIGH);  
digitalWrite(11,HIGH);  
digitalWrite(10,HIGH);  
digitalWrite(9,HIGH);  
digitalWrite(8,HIGH);  
break;  
case 1:  
Speed(139);  
digitalWrite(13,LOW);  
digitalWrite(12,LOW);  
digitalWrite(11,HIGH);  
digitalWrite(10,HIGH);  
digitalWrite(9,HIGH);  
digitalWrite(8,HIGH);  
break;  
case 2:  
Speed(168);  
digitalWrite(13,LOW);  
digitalWrite(12,LOW);  
digitalWrite(11,LOW);  
digitalWrite(10,HIGH);  
digitalWrite(9,HIGH);  
digitalWrite(8,HIGH);  
break;  
case 3:  
Speed(197);  
digitalWrite(13,LOW);  
digitalWrite(12,LOW);  
digitalWrite(11,LOW);  
digitalWrite(10,LOW);  
digitalWrite(9,HIGH);  
digitalWrite(8,HIGH);  
break;  
case 4:  
Speed(226);  
digitalWrite(13,LOW);  
digitalWrite(12,LOW);  
digitalWrite(11,LOW);  
digitalWrite(10,LOW);  
digitalWrite(9,LOW);  
digitalWrite(8,HIGH);  
break;  
case 5:  
Speed(255);  
digitalWrite(13,LOW);  
digitalWrite(12,LOW);  
digitalWrite(11,LOW);  
digitalWrite(10,LOW);  
digitalWrite(9,LOW);  
digitalWrite(8,LOW);  
break;  
case -1:  
Speed(0);  
digitalWrite(13,HIGH);  
digitalWrite(12,HIGH);  
digitalWrite(11,HIGH);  
digitalWrite(10,HIGH);  
digitalWrite(9,HIGH);  
digitalWrite(8,HIGH);  
break;  
}  
  
}  

void Speed(int S)  
{  
analogWrite (5,S);  
analogWrite (6,0);  
}  
***
