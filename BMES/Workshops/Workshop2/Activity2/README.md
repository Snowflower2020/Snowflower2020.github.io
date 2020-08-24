# Activity 2 - LED Flashing

### Task:
Have the yellow LED turned on, then every 5 seconds turn off the yellow LED and have the red LED flash 10 times.

### Circuit:
![Circuit](https://Snowflower2020.github.io/BMES/Workshops/Workshop2/Activity2/W2A2_Circuit.png)

### Code: 

```c++
int Red = 2;    // Red LED is pin 2
int Yellow = 6;	// Yellow LED is pin 6

void setup()
{
  pinMode(Red, OUTPUT);		// Define Red as output
  pinMode(Yellow, OUTPUT);	// Define Yellow as output
  digitalWrite(Red, LOW);	// Initialize Red LED as off
  digitalWrite(Yellow, HIGH);// Initialize Yellow LED as on
}

void loop()
{
  int time = millis();	
  delay (5000);
  digitalWrite(Yellow,LOW);
  for (int i = 1; i <= 10; i++)
  {
    blink();
  }
  digitalWrite(Yellow,HIGH);
}

// Write a function for blinking
void blink()
{
  digitalWrite(Red,HIGH);
  delay(500);
  digitalWrite(Red,LOW);
  delay(500);
}
```
