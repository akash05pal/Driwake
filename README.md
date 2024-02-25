# Driwake


hardware code:-

#define sensorPin A0


#define buzzerPin 3


#define relayPin 2


void setup() {

  
  // put your setup code here, to run once:
  
  
  pinMode(sensorPin, INPUT);
  
  
  pinMode(buzzerPin, OUTPUT);
  
  
  pinMode(relayPin, OUTPUT);
  
  
  Serial.begin(9600);


}



void loop() {

  
  // put your main code here, to run repeatedly:
  
  
  int val = digitalRead(sensorPin);
  
  
  Serial.println(val);

  static int cnt = 0;

  digitalWrite(relayPin, HIGH);

  if (val == 0) {
  
    
    cnt = 0;
    
    
    digitalWrite(buzzerPin, LOW);
  }
  
  else {
  
    cnt += 1;
    
    if (cnt >= 375) {
    
      digitalWrite(buzzerPin, HIGH);
      
      digitalWrite(relayPin, LOW);
    
    }
  
  }

}
