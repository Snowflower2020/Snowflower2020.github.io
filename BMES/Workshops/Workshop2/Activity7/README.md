# [Workshop 2](https://Snowflower2020.github.io/BMES/Workshops/Workshop2)

## Activity 7 - Three LEDs

### Task:
You have one button and three separate LEDs. When you hold the button, the first LED turns on. If you are still holding the button after one second, the second LED also turns on. If you are still holding the button after two seconds, the third LED also turns on. If at any point you release the button, only the LEDs that have been turned on stay on. The next time you press the button, all the LEDs will turn off. Further button presses will continue the pattern.
Hint: Don’t use delays [delay() will stall your code for the specified time]. Instead, think of a way to track time elapsed from the first button press using millis().
### Circuit:
![Circuit](https://Snowflower2020.github.io/BMES/Workshops/Workshop2/Activity7/W2A7.png)
### Code: 

```c++
// Set pin variables 
int RedLED = 7; 
int YellowLED = 4; 
int GreenLED = 2; 
int Button = 12; 
int holdTime;
int elapsedTime;
bool on = false;
int previous = 0;

void setup() 
{  
 // Initialize LEDs at output
 pinMode (RedLED, OUTPUT); 
 pinMode (YellowLED, OUTPUT); 
 pinMode (GreenLED, OUTPUT); 	
 // Initialize Button as input
 pinMode (Button, INPUT);
 // Start with LEDs off 
 digitalWrite(RedLED, LOW);
 digitalWrite(YellowLED, LOW);
 digitalWrite(GreenLED, LOW);
}

void loop() 
{
  if (digitalRead(Button) == HIGH)
  {
    digitalWrite(RedLED, HIGH);
    holdTime = millis();
    while(digitalRead(Button) == HIGH)
      {
      elapsedTime = millis()- holdTime;
      if (elapsedTime >= 1000)
      {
        digitalWrite(YellowLED, HIGH);
      }
      if (elapsedTime >= 2000)
      {
        digitalWrite(GreenLED, HIGH);
      }
    }
  }
  digitalWrite(RedLED, LOW);
  digitalWrite(YellowLED, LOW);
  digitalWrite(GreenLED, LOW);
}
```
