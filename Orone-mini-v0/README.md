Orone-mini designs
==================

Orone-mini's are designed to be software and mostly hardware compatible with LeafLabs Maple-mini. Some improvements have been inspired by Siy's mini48. These boards were also inspired  by the availability of STM32F303 in 48pin LQFP packages. Please note, boards will be tested first using STM32F103 before STM32F303 testing.


Maple-mini improvements
-----------------------
LeafLabs Maple-mini is a very impressive and useful Open Source Hardware development board. It offers approximately 4x more memory and CPU performance than an Arduino UNO, much improved peripherals, and about 50% more I/O pins in a tiny package that fits into a 40pin DIL IC socket. It is supported by an Open Source IDE and library similar to the Arduino UNO. 

However there are areas that can be improved:  
1.	DIY-assemblable; this is outlined below  
2.	Robust operation above 6V while providing current to e.g. LEDs and electronics  
3.	USB Electro-static Discharge (ESD) protecting the Host PC and Orone-mini  
4.	Socket for easier-to-connect external power  
5.	Power-on indicator  

These boards are designed to be DIY-assemblable, but otherwise software and signal compatible with Maple-mini. 

All designs are breadboard-friendly form-factors; all pins are on breadboard 0.1" grid. However, initial designs have header pins spaced 0.8" apart, wider than Maple-mini's 0.6" header pins.


*	**Orone-mini-S8A-v0r001** - Maple-mini compatible STM32F development board.  
	*Format*: two 20pin headers 0.8" apart. 1206 Components, SOT-223 voltage regulator uses LM2937-style, 'tab-is-ground', footprint  
	Improves on all 5 areas  
	Not yet tested.


*	**Orone-mini-S8C-v0r001** - Maple-mini compatible STM32F development board.    
	*Format*: two 20pin headers 0.8" apart. 1206 Components (C1 is 2917/7343), SOT-223 voltage regulator uses LM2937-style, 'tab-is-ground', footprint  
	Essentially this is Orone-mini-S8A-v0r001, and so incorporates all the same improvements. However, it uses a much larger case size for C1, the supply smoothing capacitor to reduce cost, and simplify sourcing of a suitable part. C1 is 100uF/16V, Maple-mini 1206-case size has been replaced by 2917 (7343 Metric) case size.  

	Not yet tested.


Maple-mini Software compatibility
---------------------------------
Orone-mini boards are designed to be completely software and bootloader compatible with Maple-mini. So all existing Maple-mini software should work.


Maple-mini Hardware compatibility
---------------------------------
Orone-mini-S8x boards are not physically compatible with Maple-mini because the pin headers have been moved from 0.6" spacing to 0.8" spacing. This was a result of the increased component size used on Orone-mini. The increased component size is driven by the aim to make Orone-mini DIY-assemblable. 

All Orone-mini have one change to the header pins. The Maple-mini's 'av+' power was supplied by a small voltage regulator which might close down, or be damaged when the Maple-mini was used with a power supply voltage higher than USB's voltage. Orone-mini supplies power to the 'av+' pin from a slightly larger capacity voltage regulator. The intent is to avoid damage to the small voltage regulator. However this feature has not been adequately tested yet.

The orone-mini silk screen is larger-size text, and hence contains less information, than Maple-mini. The increase in size is intended to be easier to read, and easier for PCB makers to produce.


DIY-assemblable
---------------
The Maple-mini uses a 4-layer Printed Circuit Board, which can not be modified with the 'free' version of Eagle ECAD, and is also relatively expensive. Hence, this board is a 2-layer board which can be modified using 'free' Eagle ECAD, and should be much lower cost to manufacture. The board is designed to comply with all Eagle Design Rules from OSHPark.com and Seeedstudio (see Design Rules below)

Many of the Maple-mini parts are very small '0402' size. These have been replaced by 1206 (nine times bigger). This necessitated the increase in board size, which caused the spacing between pin-headers to be increased from 0.6" to 0.8". However 1206 is a component size used in UK schools to introduce children to assembling SMD boards, so I hope will be well within the ability of most people. 

There is one small part used for Electro-Static Discharge (ESD) protection. This is only available in one package, and has some electrical advantages over alternatives, so it has been used. Maple-mini has no ESD protection, so this is a new part.

The Maple-mini has SMD parts on both sides of the board. This is relatively difficult to make using some DIY-friendly SMD techniques. Hence all 'top' SMD components have been change to 'thru-hole' allowing for a wider range of SMD assembly techniques. The specific components effected are the USB socket, buttons and LEDs. It is also hoped that the thru-hole components will be more robust than the original SMD components.

PCB Design Rules
----------------------
The Printed Circuit Boards (PCBs) have been designed using the manufacturing tolerances supported by OSHPark.com and Seeedstudio 'Fusion PCB service'. 

There are several sets of Design Rule check errors which are flagged by Eagle. None of these prevent the board being made:  

1.	There is a 'bridge' which is flagged as an error, but is manufacturable. The bridge is two touching pieces of copper, and looks like a piece of copper track. It is used to create a separate ground layer around the crystal oscillator. The separate ground should significantly reduce electrical noise transmission from the crystal oscillator. Eagle treats the bridge as two overlapping tracks, and flags clearance and overlap errors. These should be safe to ignore.  

2.	Vias within the 'tab' pin of the REG1 regulator cause DRC errors. They have no impact on manufacturing the PCB, and can be ignored. The vias should conduct heat through to the larger area of copper on the reverse side of the board. There are several other 'heat-path vias' in the component side copper pour, but vias in REG1 tab-pin should be more effective. Note the vias are placed just beyond the edge of the tab-pin to reduce the likelihood of 'voids' under the pin.  

3.	OSHPark Design Rules prevent do not cover *any* vias with solder mask. Hence any text for a silk screen (including tNames and bNames) which print across vias are flagged as "Stop Mask errors".  The appropriate resolution is to set the DRC check->Masks->Limit to 20mil, which will cover vias with a 20mil or smaller (0.5mm) drill with solder mask (tented vias).  


Thanks to
---------
Mark Rafter and Jeff Smith; Pete Harrison, Tony Wilcox, Chris Evans and David Hannaford of Midlands Micromouse and Robotics Club for advice, encouragement and expertise; Keith, Pete and Bill of Techwizz for discussions and feedback; Siy, feurig, ala42, Crenn, and everyone who contributed at LeafLabs forum. Special thanks to LeafLabs for developing the Maple-IDE and Maple-mini.
