# LoopController
Magnetic Loop Controller based on the popular design by Loftur E. Jonasson, TF3LJ / VE2AO
https://sites.google.com/site/lofturj/13-to-automatically-tune-a-magnetic-loop-antenna
https://groups.io/g/loopController

This is the smallest possible footprint for the Magnetic Loop Controller which makes possible the use in portable situations.
The project consists of 2 printed circuit boards 77 x 56.5mm. One board holds all components including 4x20 77x47mm LCD character display and Teensy 3.2/4.0 and DRV8825 stepper motor driver.


3D render of the component side of the main board 
![back-controller](https://github.com/user-attachments/assets/704977f6-1064-4351-9973-b99f6377c656)

3D render of the component side of the SWR daughter board 
![back-swr](https://github.com/user-attachments/assets/84016753-d76d-4f4f-b516-e0196b1b96ee)

The boards may be ordered populated with all SMD components from JLCPCB https://jlcpcb.com/ included here are the files including gerbers to order your board(s). 

Main Controller Board:
Gerbers
[Magnetic_Loop_Controller_1.0.zip](https://github.com/user-attachments/files/19380353/Magnetic_Loop_Controller_1.0.zip)

BOM File
[bom.csv](https://github.com/user-attachments/files/19380357/bom.csv)

Positions File
[positions.csv](https://github.com/user-attachments/files/19380376/positions.csv)


SWR Daughter Board:
Gerbers
[Magnetic_Loop_Controller_SWR_Option_1.0.zip](https://github.com/user-attachments/files/19380380/Magnetic_Loop_Controller_SWR_Option_1.0.zip)

BOM File
[bom.csv](https://github.com/user-attachments/files/19380385/bom.csv)

Positions File
[positions.csv](https://github.com/user-attachments/files/19380386/positions.csv)

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
2. Included zener diodes to protect inputs from vacuum capacitor limit switches.
3. Joined A12 to A11 of Teensy 4.0 so you can possibly use ON5IA Teensy 4.0 firmware as-is.
4. Added common tactile push buttons on-board.
5. Added power switch on board (ALPS type)
6. Added trace so if you use a Rotary Encoder with a push button it will function as Menu/Confirm.
7. Added SMD RJ45 Ethernet connector for easy connection to the stepper motor and limit switches using standerd Ethernet cable.
8. Miniature LCD character Display with backlight can be connected directly to the main controller board by 4 M3 screws.
9. Optional SWR board piggybacks on the back of the main board.
New Controller Schematic
![Schematic-controller](https://github.com/user-attachments/assets/7b553e8a-0baa-4a13-b755-a610c47f3ed1)
SWR bridge daughter board schematic
![Schematic-swr](https://github.com/user-attachments/assets/c450c20a-d48b-4b8d-a5e6-4497ec0cff0e)



Full list of additional parts to follow...

73s Al
