# Cryptid Expansion Board Instructions

Before starting, verify that you have all of the components. If anything is missing contact me (distinctm1nd) on discord. Also, contact me if you have any questions before / during the assembly process. 

Contact lavaman on discord if you would like a 3d printed back for this board. 

## Components

- Cryptid pcb
- 4 transistors
- 2- 33uF capacitors (marked with green marker)
- 2- 100uF capacitors
- 16- SMD 1206 yellow LEDs (unmarked)
- 6- SMD 1206 orange LEDs (marked with black marker)
- 2- SMD 1206 red LEDs (marked with red marker)
- 2 TH LEDs red
- 2 TH LEDs - multicolor fast flash
- 11- 68 ohm SMD 1206 resistors (marked with 68R0)
- 2- 15 ohm SMD 1206 resistors (marked with 15R0)
- 4- 10k ohm SMD 1206 resistors (marked with 1002)
- 3- 20 pin female shrouded connectors
- 16- 8 pin male headers
- 1- 10k ohm potentiometer
- 20 pin connector cable
- 1- AA battery holder
- 2- AA batteries

### Optional:

I’m including a list of resistor / LED pairings so that you can customize the LED colors, if desired. You’ll need to supply your own LEDs/resistors for any changes. If you don’t wish to customize the LED colors, skip to the assembly instructions. Be sure that you are certain about the colors you want in the forehead area if you change them. I’ve had trouble removing components from this area without damaging the board. 

If you don’t have experience selecting current limiting resistors for LED circuits, I recommend only changing D1 - D6.

There are many calculators available to calculate the current limiting resistor for a series resistor/LED circuits such as this one: https://ledcalculator.net/

R1 - R6 are in series with their respective LEDs (D1 - D6). 

So, for instance, if you want to change D1 from Red to multi-color flash you will need the ‘forward voltage’ and ‘forward current’ of the multi-color flash LED (forward voltage: 3-3.3v and forward current: 20mA). Note: this may not always be the case so consult the documentation for the specific LED you are using. You can then use the calculator to calculate the minimum required resistor. In this application, the Power Source is 3.3 volts, so you would enter:

Power supply voltage (V): 3.3
LED voltage drop (V): 3.0 (assuming this is the forward voltage of your LED)
LED current rating (mA): 20 (assuming this is the forward current of your LED)

Which gives 15 ohms. This is the minimum required resistance to guarantee that you will not burn up the LED. You can use a larger resistance than this and it will have the effect of dimming the LED. 

R7, R8 and R17 provide resistance for multiple LEDs in parallel. For instance, R7 is in series with 3 parallel LEDs (D20, D21, and D22). 

The calculation for these resistors is different from the calculation above. You can dig into the details here (https://www.nutsvolts.com/magazine/article/calculating_current) or you can use the same calculator as above and enter the information assuming that you only have one LED. This will calculate a larger resistance than you need but will be safe to use with the LEDs.  If you change any of these LEDs, they must have the same forward voltage and forward current. For instance, if you change D20 to a different color, you must also change D21 and D22 to the same color (or a color that has the same forward voltage and current as the color you have chosen). Preferably, also use LEDs from the same manufacturer / batch with the shared resistor. LED voltage and current can vary (even within the same color) and so it is always a risk to combine them in parallel without their own resistor. 

|**LED**|**Resistor**|**Location -  Color Provided in kit**|
|--- |--- |--- |
|D1 (through-hole) | R1 | Left cheek - Red|
|D2 (through-hole) | R2 | Left upper lip - multicolor flash|
| D3 (through-hole) | R3 |Right upper lip - multicolor flash|
|D4 (through-hole) |R4 | Right cheek - Red|
|D5, D6 (SMD) | R5, R6 | Eye - red|
|D20,  D21, D22 (SMD, reverse mount) | R7 |Reverse mount LEDs in circle, right side of forehead - yellow |
| D23, D24, D25 (SMD, reverse mount) |R8 |Reverse mount LEDs in circle, left side of forehead - yellow |
|D26, D27, D28 (SMD, reverse mount) |R17 |Reverse mount LEDs at top of board -  orange|

Changing the LEDs that make up the flashy circuit in the forehead (listed below) is at your own risk. It has been finicky with some LED combinations. If you want to change them, I recommend sticking with colors that have the same forward voltage / forward current. For instance, the yellow and orange LEDs that I provided both have a forward voltage of 2-2.2 volts and forward current of 20 mA. I did build one with a blue/green color combo (replace all yellow LEDs with blue and all orange LEDs with green) so I can verify that this color combination works as well. Both LEDs (blue/green) have a forward voltage of 3-3.2 volts and a forward current of 20 mA. 


|**LED**|**Resistor**|**Location -  Color Provided in kit**|
|--- |--- |--- |
|D8, D7, D9 (SMD) |R9 |Right point of flashy circuit in forehead (D8, D7 - yellow, D9- orange)|
|D16, D11, D15 (SMD) |R11 |Left point of flashy circuit in forehead (D15, D16- yellow, D11- orange)|
|D12, D17, D18, D19 (SMD) |R12 |Middle of forehead circle- yellow|
|D10, D13 D14 (SMD) |R10 |Bottom point of flashy circuit in forehead (D13, D14- yellow, D10- orange)|

Contact me on discord if you have questions. 

## Assembly Instructions:

**Be careful while soldering in the forehead area (back) not to cause a short. Use minimal solder and make sure components are aligned on the pads. The trade off of removing so much solder mask in this area is that there is an increased risk of causing a short. **

**Verify orientation of all LEDs before soldering them. **

The capacitors are non-polar so orientation for them doesn’t matter. 

Start on the back.
- Solder the 4 transistors to Q1, Q2, Q3 and Q4
- Solder the 33uF capacitors to C1 and C2 (marked with green marker)
- Solder the 100uF capacitors to C3 and C4
- Solder yellow LEDs to D7, D8, D12, D13, D14, D15, D16, D17, D18, and D19 (not marked with marker)
- Solder orange LEDs to D9, D10 (this is the LED at the bottom of the forehead triangle, the reference is covered- see image) and D11 (These LEDs make up the points of the triangle in the blinky circuit). (marked with black marker)

Move to the front.
- Solder 68 ohm resistors to R9, R10, R11, and R12
- Solder 10k ohm resistors to R13, R14, R15, and R16

At this point, if you want to verify that the blinky circuit is working, solder the potentiometer to the front left eye. Solder a 20 pin connector to the top front (marked Badge). Verify that the side with a cut out is facing down (see image):

<IMAGE>
  
Connect to the main badge for power using the included 20 pin connector. If you turn the potentiometer knob all the way clockwise, you should get a very fast blink. From here, if you turn it counter clockwise, you will get a slower blink. If the circuit does not start flashing while adjusting the potentiometer, double check the solder joints of the transistors. 

Note: The only downside of this is you can longer lay the board flat after soldering the potentiometer. I like to verify that things are working as I go along to make troubleshooting easier if something isn’t working (less components to check). This is up to you. If you want to finish the rest of the SMD components on the back before soldering the potentiometer, you can, you just won’t be able to check that things are working as you go along. 

Move to the back. 
- Solder yellow LEDs (reverse mount them) to D20, D21, D22, D23, D24, D25. Make sure to reverse mount these- you want the light shining toward the board. 

Move to the front.
- Solder 68 ohm resistors to R7 and R8

Verify that these 6 LEDs work correctly, if desired. If some of them light up but some don’t, double check LED solder joints and double check for shorts. 

Move to back: 
- Solder orange LEDs (reverse mount them) to D26, D27 and D28. Make sure to reverse mount these. You want the line shining toward the board. 

Move to front: 
- Solder a 68 ohm resistor to R17

If you did not previously solder the potentiometer to the left eye, do so now. 

Verify that everything works correctly, if desired. If the LEDs that you just soldered at the top (D26, D27, and D28) don’t light up, double check solder connections and double check for shorts. 

Move to front: 
- Solder 68 ohm resistors to R1 and R4. 
- Solder 15 ohm resistors to R2 and R3
- Solder red through-hole LEDs to D1 and D4 (the reference labels are on the back)
- Solder multi-color fast flash through-hole LEDs to D2 and D3 (the reference labels are on the back)
- Trim the LED wires on the back. 
- Solder 68 ohm resistors to R5 and R6

Move to back:
- Solder red LEDs to D5 and D6 (these are marked with red marker)

Verify that everything works correctly. 

Move to the front: 
- Solder the 16- 8 pin headers for the minibadges. The easiest way to solder these is to clip the headers into a minibadge so that you can use the minibadge to angle them correctly. 
- Solder the remaining 20 pin connectors to the second one from the top (labeled battery) and the bottom left corner. (make sure to solder them to the front of the board and make sure that the cut slot is facing down- same as before) 

Move to the back:
- Solder the battery holder. 
- Trim the battery holder wires on the front. 

### Optional but highly recommended: 
If you are planning to get a 3d printed back from Lavaman, hold off on this step until you have your back. You may not need to do this step to get good light coverage with the back on the badge. 
This step is to apply hot glue over the LEDs/mask area on the forehead and also hot glue over the LEDs/ mask on the right eye. 
The hot glue helps disperse the LED light so that it shines through the mask area with better coverage. 

## How to Use:

You can either power the expansion board with a main conference badge or with batteries. If you power the extension board with your main conference badge, the clock pin will work. If you power with batteries, the clock pin will not work. 

To power with the main conference badge or another extension board, connect the top connector (labeled Badge) to your main badge. 

<IMAGE>

DO NOT CONNECT YOUR MAIN CONFERENCE BADGE TO THE CONNECTOR LABELED BATTERY (LOWER ONE). ONLY CONNECT THE MAIN BADGE TO THE TOP CONNECTOR. IF YOU CONNECT YOUR MAIN BADGE TO THE LOWER ONE WITH BATTERIES YOU MAY DAMAGE BOTH BADGES. 

<IMAGE>

To power with batteries, connect the connectors labeled Badge and Battery together.

You can add additional extender boards by connecting them to the connector at the bottom left corner. 

Rotate the potentiometer to adjust the rate of the flash. 
