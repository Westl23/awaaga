# An interesting button

We made a a sequence of flahing LEDs reset after it meets two conditions: 
the pin (labeled LED) becoming less than 9 and
the button being pressed.

Once the two conditions are met, the LED would then return to its beginning pin number (13) and continue its flashing sequence (until the two conditions are met again).

This is the code for it:

int LED = 13;
int button = 2;
int buttonState = 0; 

void setup() {
  Serial.begin(9600);

}

 void loop(){
  delay(100);
  buttonState = digitalRead(button);
  pinMode(LED, OUTPUT);
  pinMode(button, INPUT);

  digitalWrite(LED, HIGH);
  delay(100);
  digitalWrite(LED, LOW);
  delay(100);
  LED = LED - 1;

  if(LED < 9 && buttonState == HIGH){
    LED = 13;
    Serial.write(" Reset!! ");
  } 
 }
