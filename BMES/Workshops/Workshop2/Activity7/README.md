# [Workshop 2](https://Snowflower2020.github.io/BMES/Workshops/Workshop2)

## Activity 5 - LED Three Presses

### Task:
Have an LED toggle on/off after three clicks of a button.

### Circuit:
![Circuit](https://Snowflower2020.github.io/BMES/Workshops/Workshop2/Activity7/W2A7.png)
### Code: 

```c++
int LED = 2; 
int Button = 7; 
bool on = false;
int previous = 0;
int BC = 0;

void setup() 
{  
 pinMode (LED, OUTPUT); 	
 pinMode (Button, INPUT); 	
 digitalWrite(LED,LOW);	
}

void loop() 
{
  
  int current = digitalRead(Button); 
  if (current != previous)			
  {
    buttonClicks++;	
  	
    if (digitalRead(Button) == HIGH && on == false && BC % 3 == 0)
  	 {
  	  digitalWrite(LED, HIGH);
  	  on = true;
 	 }
 	else if (digitalRead(Button) == HIGH && on == true && BC % 3 == 0) 
 	 {
 	   digitalWrite(LED, LOW);
 	   on = false;
 	 }
  }
  previous = current; 
}
```
