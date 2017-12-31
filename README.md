#include <SoftwareSerial.h>          
    SoftwareSerial mySerial(10, 11); // RX, TX 配置10、11为软串口    
void setup()    
    {    
      // Open serial communications and wait for port to open:    
      Serial.begin(9600);    
     // while (!Serial) {    
        ; // wait for serial port to connect. Needed for Leonardo only    
     // }    
        
      // set the data rate for the SoftwareSerial port    
     //pinMode(10,INPUT_PULLUP);   
    // pinMode(11,INPUT_PULLUP);   
      mySerial.begin(9600);    
    }    
        
    void loop() // run over and over    
    {    
      if (mySerial.available())    
        Serial.write(mySerial.read());    
      if (Serial.available())    
        mySerial.write(Serial.read());    
    }  
