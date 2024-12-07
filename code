
const int sensorTempPin = A0;
const int motorPin = 9;     
const int ledPin = 7;        
const int buzzerPin = 8;      


const float limiteVentilador = 30.0;
const float limiteEmergencia = 50.0; 

void setup() {
  pinMode(motorPin, OUTPUT);
  pinMode(ledPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // Leitura do sensor de temperatura 
  int leituraAnalogica = analogRead(sensorTempPin);
  float tensao = leituraAnalogica * (5.0 / 1023.0); 
  float temperatura = (tensao - 0.5) * 100.0; 

  Serial.print("Temperatura: ");
  Serial.print(temperatura);
  Serial.println(" °C");

  // Controle do ventilador
  if (temperatura >= limiteVentilador) {
    digitalWrite(motorPin, HIGH); 
  } else {
    digitalWrite(motorPin, LOW); 
  }

  // Alerta de emergência
  if (temperatura > limiteEmergencia) {
    digitalWrite(ledPin, HIGH);  
    digitalWrite(buzzerPin, HIGH); 
  } else {
    digitalWrite(ledPin, LOW);   
    digitalWrite(buzzerPin, LOW);
  }

  delay(1000);
}
