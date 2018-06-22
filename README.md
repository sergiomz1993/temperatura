//# temperatura




///programación temperatura.


#include <LiquidCrystal.h>          //Incluir esta libreria para poder usar el lcd

int Ana1 = A0;                      //Entrada analogica de LM35
LiquidCrystal lcd(12,11,5,4,3,2);   //Definimos la pantalla LCD
 int Temp = 0;
 int Sensor = 0 ; 
char Grados = 'º';

void setup(){
  Serial.begin(9600);      
  lcd.begin(16,2);  
  pinMode(13,OUTPUT);
  digitalWrite(13, HIGH);          //Activamos la retroiluminacion
}

//void loop(){
  
  //Temp = analogRead(Ana1);                  //detectamos el valor de la entrada analogica que muestra el sensor lm35
  //Temp = map(Temp,0,1024,-55,150);         //Escalamos la señal a grados centigrados
  
  //Mostramos los grados en el serial
 // Serial.print("Grados: ");
  //Serial.print(Temp);
  //Serial.print(Grados);
  //Serial.println("C");

  void loop()
   {    int lectura = analogRead(Sensor);
        float voltaje = 5.0 /1024 * lectura ; 
        float Temp = voltaje * 100  ;
        Serial.println(Temp) ;
        Serial.print(Grados);
        Serial.println("C");
        delay(200);
   
  
  //Mostramos los grados en  lcd

  
  lcd.setCursor(0,0);            // lectura lcd


  lcd.print("Temperatura: ");
  lcd.setCursor(0,1);            
  lcd.print(Temp); 
  
  
  delay(1000);                  //temperatura 
}
