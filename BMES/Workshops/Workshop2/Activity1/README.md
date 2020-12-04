# [Workshop 2](https://Snowflower2020.github.io/BMES/Workshops/Workshop2)

## Activity 1 - LED Time

### Task:
Turn the LED on after 5 seconds using a conditional statement. (Note: Don’t use delay(). Make a variable: int time)

### Circuit:
![Circuit](https://Snowflower2020.github.io/BMES/Workshops/Workshop2/Activity1/W2A1_Circuit%20(2).png)

### Code: 

```c++
int LED1 = 2;   // Define LED1 as pin 2

void setup()
{
  pinMode(LED1, OUTPUT);    // Define LED1 as an output
  digitalWrite(LED1, LOW);  // Initialize LED1 as off	
}

void loop()
{
  // Define variable time to hold milliseconds elapsed
  int time = millis();  
  if (time >= 5000)		     
  {
    digitalWrite(LED1,HIGH);	// Turn LED on
  }
}
```
