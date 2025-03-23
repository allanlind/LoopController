Magnetic Loop Controller based on the popular design by Loftur E. Jonasson, TF3LJ / VE2AO

https://sites.google.com/site/lofturj/13-to-automatically-tune-a-magnetic-loop-antenna
https://groups.io/g/loopController

This is the smallest possible footprint for the Magnetic Loop Controller which makes possible the use in portable situations.
The project consists of 2 printed circuit boards 77 x 56.5mm. One board holds all components including 4x20 77x47mm LCD character display and Teensy 3.2/4.0 and DRV8825 stepper motor driver, and a second board is piggybacked on for SWR measurement.


3D render of the component side of the main board 
![back-controller](https://github.com/user-attachments/assets/c84b877e-9d73-43b1-9863-8d7a48a9955a)

3D render of the component side of the SWR daughter board 
![back-swr](https://github.com/user-attachments/assets/716ac14b-6500-4749-b082-0e0688e89a87)


The boards may be ordered populated with all SMD components from JLCPCB https://jlcpcb.com/ included here are the files including gerbers to order your board(s). 

Main Controller Board:
Gerbers
[Magnetic_Loop_Controller_1.1.zip](https://github.com/user-attachments/files/19400983/Magnetic_Loop_Controller_1.1.zip)

BOM File
[bom.csv](https://github.com/user-attachments/files/19400980/bom.csv)

Positions File
[positions.csv](https://github.com/user-attachments/files/19400978/positions.csv)




SWR Daughter Board:
Gerbers
[Magnetic_Loop_Controller_SWR_Option_1.1.zip](https://github.com/user-attachments/files/19406529/Magnetic_Loop_Controller_SWR_Option_1.1.zip)

BOM File
[bom.csv](https://github.com/user-attachments/files/19406530/bom.csv)


Positions File
[positions.csv](https://github.com/user-attachments/files/19406531/positions.csv)


Loftur's original code should run as-is if using a Teensy 3.2
Some changes to the code will be required to use a Teensy 4.0 see ON5IA [Running the Automatic Magnetic Loop Tuner on a Teensy 4.0 – Golb.be – ON5IA  ](https://www.golb.be/running-the-automatic-magnetic-loop-tuner-on-a-teensy-4-0/)
Some short comings of Loftur's oringinal PCB design are:
1. Many connectors and ribbon/wires required to connect up the display, buttons, power etc.
2. No on-board reverse polarity protection for 12V input.
3. lots of through hole components to be soldered.
4. Only works with Teensy 3.2 which is no longer in production.
5. No built-in SWR detection.

Internal view of Loftur's original controller:
![Loftur_original_photo](https://github.com/user-attachments/assets/ed87f680-dc14-40b1-ac3b-0c79518e38c2)
Schematic of Loftur's design
![Loftur_original_schematic](https://github.com/user-attachments/assets/27cbc087-f75f-40cc-ab1e-b2943080d432)


Features added.
1. Added 1k resistors to all data lines between the Teensy, LCD and DRV8825 to minimize risk of 5V levels destroying the Teensy 4.0.
2. Changed to 3.3V zener diodes to protect Teensy 4.0 inputs from possible damaging voltages on vacuum capacitor limit switch lines.
3. Joined A12 to A11 of Teensy 4.0 so you can possibly use ON5IA Teensy 4.0 firmware as-is.
4. Added common tactile push buttons on-board.
5. Added power switch on board (ALPS type)
6. Added trace so if you use a Rotary Encoder with a push button it will function as Menu/Confirm.
7. Added SMD RJ45 Ethernet connector for easy connection to the stepper motor and limit switches using standerd Ethernet cable.
8. Miniature LCD character Display with backlight can be connected directly to the main controller board by 4 M3 screws.
9. Optional SWR board piggybacks on the back of the main board.
New Controller Schematic
![Schematic-controller](https://github.com/user-attachments/assets/72d82677-31e2-4d0c-af53-aab60de28600)

SWR bridge daughter board schematic
![Schematic-swr](https://github.com/user-attachments/assets/c450c20a-d48b-4b8d-a5e6-4497ec0cff0e)



Full list of additional parts: (work in progress)

LCD Display
Search Ali Express "small size 20x4 2004 77x47mm Lcd Display Module HD44780 5V"
![LCD](https://github.com/user-attachments/assets/617c22e9-360b-4e16-842f-a926fce3d058)

Connectors for LCD Display
Female Header:  XKB Connection X5511FV-16-C30D743-0743 LCSC Part number C2764599 
Male Header (solder to controller PCB): XKB Connection X5511WV-16-C35D35-1000 LCSC Part number C2764600

Main Power switch: Alps ALPINE SPEF110100 LCSC Part number C115366

Push buttons 6mm tactile CUI TS02-66-170-BK-100-SCR-D LCSC Part number C4364522 or Samesky TS02-66-170-BK-100-SCR-D Mouser No:179-TS0266170BK100SC these are 17mm shaft but probably need longer shaft (depends on what we decide for the case)

Main power connector: Boom Precision Elec DC-005 2.0 LCSC Part number C16214 

CAT Audio connector: XKB Connection PJ-32000 LCSC Part number C2689690

5V Regulator: ST Microelectronics L7805CV-DG LCSC Part number C3795

Rotary Encoder: EM14A0D-C24-L64N Mouser part number  652-EM14A0D-C24-L64N

DRV8825 Stepper Motor Driver Carrier, High Current https://www.pololu.com/product/2133 (suggest you glue a heatsink to the chip)

Teensy 4.0 Fully Loaded https://protosupplies.com/product/teensy-4-0-fully-loaded/

You'll need two 14 square hole female headers and a 2x5 header for the Teensy 4.0


Pinout for RJ45 connector
Orange and Green pair are for stepper motor windings
Brown and Blue pair are for limit switches

![RJ45](https://github.com/user-attachments/assets/2ac93663-9a04-4dbe-a8be-6afd55b50617)


73s Al
