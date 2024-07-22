# Project Name : 4 Digit Display Counter using VSDsquadron RISC-V Dev. Board with TM1637 Driver via I2C Protocol.

**1. Overview :-**

This project explains how to build a 4-digit counter with the VSDsquadron RISC-V development board and the TM1637 display driver. The communication between the development board and the display driver is facilitated via the I2C protocol, allowing efficient and reliable data transfer.The VSDsquadron Board is powered by CH32V003 chip with 32 RISC-V core based on RV32CE Instruction set which is operated under 24Mhz clock freqeuncy.with very high speed memory : 2KB SRAM for volatile data storage ,16KB code flash for programme memory.it
has on board programmer chip CH32V305 where code deployment and debugging is done.

**2. Components Required :-**

- VSDSquadron Mini RISC-V development board
- USB cable Type C
- TM1637 ( Display Driver)
- 4 Jumper wires with diffrent colour 
- Development environment ( Arduino IDE)

**3. Development Environment Setup Steps:-**
   
  - Open the Arduino IDE.
  - Install TM1637 library in Arduino IDE
  - Go to File > Preferences.
  - In the "Additional Board Manager URLs" field, add the following URL
    https://github.com/openwch/board_manager_files/raw/main/package_ch32v_index.json
  - select tools ----> Boards ----> CH32 MCU EVT Boards ---->CH32V00x
  - Install OpenOCD: This is used for flashing the program to the board.
  - Drivers: Ensure you have the correct USB drivers installed for your operating system.

**4.1 Circuit Connection :**

   - PD4 GPIO Pin is connected to Clk pin of TM1637 Driver 
   - PD2 GPIO Pin is connected to DIO (Data Input Output ) of Display Driver(TM1637)
   - Power supply (5V ) is given to VCC Port of Display Driver
   - and there some ground pin connections.

4.2 **Pin connection Table :**

	| TM1637 Display Driver | VSDsquadron Board   |
	|-----------------------|---------------------|
	| CLK                   | PD4 (GPIO Pin)      |
	| DIO                   | PD2 (GPIO Pin)      |
	| VCC                   | 5V                  |
	| GND                   | GND                 |


 **5. Circuit Design with pin connection:**

![connection_bord](https://github.com/user-attachments/assets/0509f23f-774f-4807-a4a5-7af972e651e4)


**4. Application code (C code ) for count sequence (0000 to 9999 ):-**

```sh
#include<TM1637Display.h>
#define CLK PD4
#define DIO PD2

TM1637Display display(CLK,DIO);

void setup() {
  // initilise the display
  display.setBrightness(4);

}

void loop() {
  //  main code , to run repeatedly:
  for(int i =0;i<=9999;i++)
  {
    display.showNumberDec(i,true);
    delay(100);
  }

}
   ```

**5. Led Blinking Video:**

   [https://drive.google.com/drive/u/0/folders/1SaBz9WaXcjdF0bklpkkaUuGQpa2vX_32]
