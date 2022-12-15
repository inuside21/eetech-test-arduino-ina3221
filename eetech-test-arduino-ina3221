#include <Wire.h>
#include "SDL_Arduino_INA3221.h"
#include <LiquidCrystal_I2C.h>

// ina3221
SDL_Arduino_INA3221 ina3221;
#define OUTPUT_CHANNEL1 1
#define OUTPUT_CHANNEL2 2
#define OUTPUT_CHANNEL3 3

// lcd
LiquidCrystal_I2C lcd(0x27, 16, 2); 

void setup(void) 
{
  Serial.begin(9600);
  Serial.println("SDA_Arduino_INA3221_Test");

  // ina3221 init
  ina3221.begin();
  Serial.print("Manufactures ID=0x");
  int MID;
  MID = ina3221.getManufID();
  Serial.println(MID,HEX);

  // lcd init
  lcd.begin(); //initialize the lcd
  lcd.backlight(); //open the backlight 
}

void loop(void) 
{
  // ina3221
  // ============================
  Serial.println("------------------------------");
  float shuntvoltage1 = 0;
  float busvoltage1 = 0;
  float current_mA1 = 0;
  float loadvoltage1 = 0;


  busvoltage1 = ina3221.getBusVoltage_V(OUTPUT_CHANNEL1);
  shuntvoltage1 = ina3221.getShuntVoltage_mV(OUTPUT_CHANNEL1);
  current_mA1 = ina3221.getCurrent_mA(OUTPUT_CHANNEL1);  
  loadvoltage1 = busvoltage1 + (shuntvoltage1 / 1000);
  
  Serial.print("Output Bus Voltage:   "); Serial.print(busvoltage1); Serial.println(" V");
  Serial.print("Output Shunt Voltage: "); Serial.print(shuntvoltage1); Serial.println(" mV");
  Serial.print("Output Load Voltage:  "); Serial.print(loadvoltage1); Serial.println(" V");
  Serial.print("Output Current 1:       "); Serial.print(current_mA1); Serial.println(" mA");
  Serial.println("");

  float shuntvoltage2 = 0;
  float busvoltage2 = 0;
  float current_mA2 = 0;
  float loadvoltage2 = 0;

  busvoltage2 = ina3221.getBusVoltage_V(OUTPUT_CHANNEL2);
  shuntvoltage2 = ina3221.getShuntVoltage_mV(OUTPUT_CHANNEL2);
  current_mA2 = ina3221.getCurrent_mA(OUTPUT_CHANNEL2);
  loadvoltage2 = busvoltage2 + (shuntvoltage2 / 1000);
  
  Serial.print("Output Bus Voltage 2:   "); Serial.print(busvoltage2); Serial.println(" V");
  Serial.print("Output Shunt Voltage 2: "); Serial.print(shuntvoltage2); Serial.println(" mV");
  Serial.print("Output Load Voltage 2:  "); Serial.print(loadvoltage2); Serial.println(" V");
  Serial.print("Output Current 2:       "); Serial.print(current_mA2); Serial.println(" mA");
  Serial.println("");

  float shuntvoltage3 = 0;
  float busvoltage3 = 0;
  float current_mA3 = 0;
  float loadvoltage3 = 0;

  busvoltage3 = ina3221.getBusVoltage_V(OUTPUT_CHANNEL3);
  shuntvoltage3 = ina3221.getShuntVoltage_mV(OUTPUT_CHANNEL3);
  current_mA3 = ina3221.getCurrent_mA(OUTPUT_CHANNEL3);
  loadvoltage3 = busvoltage3 + (shuntvoltage3 / 1000);
  
  Serial.print("Output Bus Voltage 3:   "); Serial.print(busvoltage3); Serial.println(" V");
  Serial.print("Output Shunt Voltage 3: "); Serial.print(shuntvoltage3); Serial.println(" mV");
  Serial.print("Output Load Voltage 3:  "); Serial.print(loadvoltage3); Serial.println(" V");
  Serial.print("Output Current 3:       "); Serial.print(current_mA3); Serial.println(" mA");
  Serial.println("");

  // LCD
  // ============================
  lcd.clear();
  lcd.setCursor(0, 0);        
  lcd.print("Current (mA)");        
  lcd.setCursor(0, 1);         
  lcd.print(String(current_mA1, 1) + "  " + String(current_mA2, 1) + "  " + String(current_mA3, 1)); // print message at (2, 1)

  delay(1000);
}
