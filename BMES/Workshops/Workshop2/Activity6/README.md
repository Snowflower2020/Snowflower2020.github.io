# [Workshop 2](https://Snowflower2020.github.io/BMES/Workshops/Workshop2)

## Activity 6- LED Blinking

### Task:
Have two LEDs blink at different rates
Have one LED blink at a randomly created rate, and the other blink half as fast
### Circuit:
![Circuit](https://Snowflower2020.github.io/BMES/Workshops/Workshop2/Activity6/W2A6.png)
### Code: 

```c++
int Blue = 2;	// Define which LED goes to which pin
int Red = 3;   // Define which LED goes to which pin

int time1 = random(500,1000);	// Random number from 500-1000
int time2 = time1/2;   			// Half as fast

void setup() 
{ 
 pinMode (Blue, OUTPUT); // initialize pin1 as output
 pinMode (Red, OUTPUT); // initialize pin2 as output
 digitalWrite(Blue,LOW); // start with LED1 off
 digitalWrite(Red,LOW); // start with LED2 off
}

void loop() 
{ 
  int time = millis();
  if (time % time1 == 0) 
  {
  	digitalWrite(Blue, HIGH);
  }
  if (time % time2 == 0) 
  {
  	digitalWrite(Red, HIGH);
  }
  else
  {
    digitalWrite(Blue, LOW);
  	digitalWrite(Red, LOW);
  }
}
```
