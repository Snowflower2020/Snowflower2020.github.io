# [Workshop 2](https://Snowflower2020.github.io/BMES/Workshops/Workshop2)
## Activity 3 - LED Button

### Task:
Have the LED light up when the button is pressed down and turn off when not.

### Circuit:
![Circuit](https://Snowflower2020.github.io/BMES/Workshops/Workshop2/Activity3/W2A4_Circuit%20(2).png)
### Code: 

```c++
int LED = 2; 
int Button = 7; 
bool on = false;
int previous = 0;

void setup() 
{  
 pinMode (LED, OUTPUT); 	// initialize pin1 as output
 pinMode (Button, INPUT); 	// initialize pin2 as input
 digitalWrite(LED,LOW);	// start with LED off
}

void loop() 
{
  if (digitalRead(Button) == HIGH)
  {
    digitalWrite(LED, HIGH);
  }
  else 
  {
    digitalWrite(LED, LOW);
  }
}
```
