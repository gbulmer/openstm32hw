Orone-mini designs
==================

Orone-mini's are designed to be software and mostly hardware compatible with LeafLabs Maple-mini. Some improvements have been inspired by Siy's mini48. These boards were also inspired  by the availability of STM32F303 in 48pin LQFP packages. Please note, boards will be tested first using STM32F103 before STM32F303 testing.


Maple-mini improvements
-----------------------
LeafLabs Maple-mini is a very impressive and useful Open Source Hardware development board. It offers approximately 4x more memory and CPU performance than an Arduino UNO, much improved peripherals, and about 50% more I/O pins in a tiny package that fits into a 48pin DIL IC socket. It is supported by an Open Source IDE and library similar to the Arduino UNO. 

However there are areas that are improved by Orone-mini designs:  
0.	Two-layer PCB, and so can be modified using 'free' Eagle CAD (unlike 4-layer which requires a commercial license)
1.	DIY-assemblable; this is outlined below  
2.	More robust main power supply for operation above 6V; better current supply to e.g. LEDs and external digital electronics  
3.	USB Electro-Static Discharge (ESD) protection for Host PC and Orone-mini,
4.	USB overvoltage protection, protecting Orone-mini's USB power connection 
5.	Extra 2-pin molex socket for easier-to-connect external power  
6.	Power-on indicator  
7.	More robust through-hole mini-USB socket  
8.	Larger silk screen for easier readability  
9.	Silk screen warns of dedicated USB pins, and shows JTAG-SWD pins for extrnal debugger  
10.	Reduced-cost of capacitor C1 by using larger size (2917/7343)  
11.	Access to all STM32F signals; two are not connected to header pins  
12.	Access to the USB input voltage (after polyfuse protection) for 5V power for external electronics  
13.	Access to diode-protected but unregulated input voltage, for external electronics     
14.	Manual control of the USB enumeration mechanism to simplify using STM32F303 manufactured-in USB bootloader. The USB 'DISC' signal, along with ground, can be accessed using a 2 x 0.1" header.  
15.	All parts are straightforward to source, and available from a variety of sources. The Bill of Materials identifies several suppliers.  


These boards are designed to be DIY-assemblable, but otherwise software and signal compatible with Maple-mini. 

All designs are breadboard-friendly form-factors; all pins are on breadboard 0.1" grid. However, initial designs have header pins spaced 0.8" apart, wider than Maple-mini's 0.6" header pins.


*	**Orone-mini-S8A-v0r001** - Maple-mini compatible STM32F development board.  
	*Format*: two 20pin headers 0.8" apart. 1206 Components, SOT-223 voltage regulator uses LM2937-style, 'tab-is-ground', footprint  
	Improves on first 5 areas  
	Successfully tested by LeafLabs forum member 'ventosus'.


*	**Orone-mini-S8C-v0r001** - Superseded by Orone-mini-S8D.    

*	**Orone-mini-S8D-v0r001** - Superseded by Orone-mini-S8E.    

 
*	**Orone-mini-S8E-v0r001** - Maple-mini compatible STM32F development board.    
	*Format*: two 20pin headers 0.8" apart.  
	*Electronics*:1206 Components except NUF2042XV6, C1 is larger 2917/7343, SOT-223 voltage regulator uses LM2937-style, 'tab-is-ground', footprint.  
	PCB requires 6mil track and 6mil space manufacturing capability  
	Similar to Orone-mini-S8A, S8C and S8D, however is physically different from Orone-mini-S8D, and so it's a new part number.  
	Incorporates ten improvements.  
	Not yet tested.

*	**Orone-mini-S8H-v0r001** - Maple-mini compatible STM32F development board.    
	*Format*: two 20pin headers 0.8" apart.   
	*Electronics*:1206 Components except NUF2042XV6, C1 is larger 2917/7343, SOT-223 voltage regulator uses LM2937-style, 'tab-is-ground', footprint.  
	PCB requires *8mil track and 8mil space* manufacturing capability    
	Similar to Orone-mini-S8A, S8C and S8D, however uses coarser, lower-cost PCB manufacturing rules.  
	Incorporates ten improvements.  
	Successfuly tested by Forum members Crenn and Adam


*	**Orone-mini-S8J-v0r001** - Maple-mini compatible STM32F development board.    
	*Format*: two 20pin headers 0.8" apart.   
	*Electronics*:1206 Components or larger, except C1 (2917/7343), SOT-223 voltage regulator uses LM2937-style, 'tab-is-ground', footprint.  
	PCB requires *8mil track and 8mil space*, 0.4mm via manufacturing capability    
	Similar to Orone-mini-S8A, S8C and S8D, however uses coarser, lower-cost PCB manufacturing rules.  
	Incorporates all improvements.  
	Not yet tested.

*	**CAM/OSHPark-Orone-mini-S8E-v0.cam** - OSHpark.com Eagle CAM file  
	Not yet tested.



Maple-mini Software compatibility
---------------------------------
Orone-mini boards are designed to be completely software and bootloader compatible with Maple-mini. So all existing Maple-mini software should work.


Maple-mini Hardware compatibility
---------------------------------
Orone-mini-S8x boards are not physically compatible with Maple-mini because the pin headers have been moved from 0.6" spacing to 0.8" spacing. This was a result of the increased component size used on Orone-mini. The increased component size is driven by the aim to make Orone-mini DIY-assemblable. 

Orone-mini-S8J pins carry identical signals to Maple-mini. Unlike Orone-mini-S8A-S8H, Orone-mini-S8J 'av+' pin is also identical to Maple-mini. Orone-mini-S8J supplies the 'av+' voltage from the analogue power regulator. The assumption is this will be a lower noise power source than the digital power supply. However this is not yet tested.

Orone-mini version S8A-S8H have one change to the header pins. The Maple-mini's 'av+' power was supplied by a small voltage regulator which might close down, or be damaged when the Maple-mini was used with a power supply voltage much higher than USB's voltage. Orone-mini S8A-S8H supplies power to the 'av+' pin from a slightly larger capacity voltage regulator. The intent is to avoid damage to the small voltage regulator. 

The orone-mini silk screen is larger-size text, and hence contains less information, than Maple-mini. The increase in size is intended to be easier to read, and easier for PCB makers to produce.


DIY-assemblable
---------------
The Maple-mini uses a 4-layer Printed Circuit Board, which can not be modified with the 'free' version of Eagle ECAD. 4-layer boards are also relatively expensive. Hence, this board is a 2-layer board which can be modified using 'free' Eagle ECAD, and the PCB should be much lower cost to manufacture. The board is designed to comply with all Eagle Design Rules from OSHPark.com and Seeedstudio (see Design Rules below)

Many of the Maple-mini parts are very small '0402' size. These have been replaced by 1206 (nine times bigger). This necessitated the increase in board size, which caused the spacing between pin-headers to be increased from 0.6" to 0.8". However 1206 is a component size used in UK schools to introduce 13yo school children to assembling SMD boards. So I hope will be well within the ability of many people. 

Earlier designs used a very small part for Electro-Static Discharge (ESD) protection. This has been replaced by a combination of larger parts, which should be less challenging to assemble. Maple-mini has no ESD protection, so this is additional functionality to Maple-mini.

The Maple-mini has SMD parts on both sides of the board. This is relatively difficult to make using some DIY-friendly SMD techniques. Hence all 'top' SMD components have been changed to 'thru-hole' allowing for a wider range of DIY SMD assembly techniques. The specific components effected are the USB socket, buttons and LEDs. The thru-hole components should also be more robust than the original SMD components.

PCB Design Rules
----------------------
The Printed Circuit Board (PCBs) has been designed using widely available PCB manufacturing tolerances, specifically 8mil track, 8mil space. The smallest drill is 0.4mm (though there is only one this size, all others are 0.5mm). These manufacturing tolerances are supported by OSHPark.com and Seeedstudio 'Fusion PCB service'. (If you use other PCB manufacturers, would you please feedback your results?)

There are several sets of Design Rule check errors which are flagged by Eagle. None of these prevent the board being made:  

1.	There is a 'bridge' which is flagged as an error, but is manufacturable. The bridge is two touching pieces of copper, and looks like a piece of copper track. It is used to create a separate ground track to the analogue power supply. Eagle treats the bridge as two overlapping tracks, and flags clearance and overlap errors. These is be safe to ignore.  

2.	Vias near the 'tab' pin of the REG1 regulator cause DRC errors. They have no impact on manufacturing the PCB, and can be ignored. The vias should conduct heat through to the larger area of copper on the reverse side of the board. There are several other 'heat-path vias' in the component side copper pour, but vias in REG1 tab-pin should be more effective. Note the vias are placed just beyond the edge of the tab-pin silk screen to reduce the likelihood of solder 'voids' under the pin.  

3.	The crystal routing is quite intricate. It contains Clearance (1), Keepout (3), Restrict (6) DRC Errors.  

4.    C5 has one Clearance DRC error with a ground via.  

5.    FUSE1 has 1 Overlap DRC error with a power via.  

6.    D1 has 1 Overlap DRC error with a via.  

7.	OSHPark Design Rules prevent via 'tenting'; Eagle generated solder mask will not cover *any* vias with solder mask. Hence any text for a silk screen (including tNames and bNames) which print across vias are flagged as "Stop Mask errors".  Small vias should be 'tented'. Set the DRC check->Masks->Limit to 20mil, which will cover vias with a 20mil or smaller (0.5mm) drill with solder mask (tented vias). The Design Rules embedded in this PCB CAD tents vias, so this is only an issue if you load OSHParks DRU file.   


Thanks to
---------
Mark Rafter and Jeff Smith; Tony Wilcox, Chris Evans and David Hannaford of Midlands Micromouse and Robotics Club for advice, encouragement and expertise; Keith, Pete and Bill of Techwizz for discussions and feedback; Siy, feurig, ala42, crenn, soycamo and everyone who shared ideas, built boards and contributed at LeafLabs forum; Laen of OSHPark.com for PCB & CAM help and expertise. Special thanks to Pete Harrison for sharing his knowledge, experience and good humour, and to LeafLabs for developing the Maple-IDE and Maple-mini.
