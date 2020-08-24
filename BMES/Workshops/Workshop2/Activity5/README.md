# [Workshop 2](https://Snowflower2020.github.io/BMES/Workshops/Workshop2)

## Activity 5 - LED Three Presses

### Task:
Have an LED toggle on/off after three clicks of a button.

### Circuit:
![Circuit](https://Snowflower2020.github.io/BMES/Workshops/Workshop2/Activity5/W2A5_Circuit.png)

### Code: 

```c++
int LED = 2; 
int Button = 7; 
bool on = false;
int previous = 0;
int buttonClicks = 0;

void setup() 
{  
 pinMode (LED, OUTPUT); 	// initialize pin1 as output
 pinMode (Button, INPUT); 	// initialize pin2 as input
 digitalWrite(LED,LOW);		// start with LED off
}

void loop() 
{
  
  int current = digitalRead(Button); // reset current as current reading
  if (current != previous)			 // check for button press (to account for holding)
  {
    buttonClicks++;	// increment button counter by 1 when button is pressed    
  	
    if (digitalRead(Button) == HIGH && on == false && buttonClicks % 3 == 0)
  	 {
  	  digitalWrite(LED, HIGH);
  	  on = true;
 	 }
 	else if (digitalRead(Button) == HIGH && on == true && buttonClicks % 3 == 0) 
 	 {
 	   digitalWrite(LED, LOW);
 	   on = false;
 	 }
  }
  previous = current; // update current value as previous value for next iteration
}
```
