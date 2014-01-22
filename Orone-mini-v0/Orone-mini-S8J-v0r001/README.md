Orone-mini-S8J-v0r001
=====================

Maple-mini compatible STM32F development board. 

This board is a significant evolution of Orone-mini-S8H. 
Specifically, the NUF2042XV6 USB EMI, termination and ESD device has been replaced. Several makers feedback that it was awkwardly small and fiddly to place.

The replacement part is an STF202-22, which is 4x bigger than the NUF2042XV6.   This STF202-22 is used in such a way that its Vusb ESD and overvoltage protection can't protect the Vusb line. So a separate TVS diode is used to protect the Vusb connection.

All earlier Orone-mini-S8x boards had the AV+ supply voltage header pin connected to the main digital power supply. This was done in order to reduce the problem which had effected Maple-mini boards of too much power being drawn from AV+, and damaging the voltage regulator. 

However, Ventosus made measurements of ADC noise, using circuits powered buy the on-board power supply. These ranked the ADC noise performance as Maple analogie supply best, then Orone-mini-S8H-v0r001's digital supply, then Maple's digital supply. 

Orone-mini-S8J-v0r001's analogue power supply has been connected to av+, to improve Orone-mini's ADC noise. 

PLEASE NOTE the av+ power supply should not be used above an input voltage of approximately 9V and 20mA, as the small voltage regulator may overheat, shutdown or be damaged.

Orone-mini-S8H's power routing and ground plane have been reworked to reduce electrical noise.


This board has not been made and tested yet. It is being released now to gather feedback, and hopefully encourage people to test it. The board has been designed for manufacture using two PCB makers. However, a goal is to ensure it is manufacturable by a wider range of PCB makers, so please feedback.

This is board designed to be DIY-assemblable, but otherwise software and signal compatible with Maple-mini. It has been inspired by some of Siy's mini48 innovations, and also the availability of STM32F303 in 48pin LQFP packages.

It is a breadboard-friendly form-factor; all pins are on breadboard 0.1" grid. Unlike Maple-mini, the two 20pin 0.1" headers are 0.8", and not 0.6" apart. However it is still narrow and short enough to fit into single breadboards.

Maple-mini C1 1206-case-size has been replaced by a 2917 (7343 Metric) case size. 
Orone-mini-S8J brings tw extra signals, and two new voltages, to header pads compared to Maple-mini. These additions do not effect any Maple-mini pins. The pads are on the same 0.1" grid as the headers.


Orone-mini improvements over Maple-mini
-----------------------
LeafLabs Maple-mini is a very impressive and useful Open Source Hardware development board. It offers approximately 4x more memory and CPU performance than an Arduino UNO, much improved peripherals, and about 50% more I/O pins in a tiny package that fits into a 40pin DIL IC socket. It is supported by an Open Source IDE and library similar to the Arduino UNO. 

However there are areas that can be improved:  
1.	DIY-assemblable - all parts are approaximately 1206 size or larger 
2.	Robust operation above 6V while providing current to e.g. LEDs and electronics  
3.	USB Electrostatic Discharge (ESD) protecting the Host PC and Orone-mini  
4.	Two-pin Molex kk Socket for easier-to-connect external power source
5.	Power-on indicator  
6.	Access to all STM32F signals; two signals are not connected to Maple-mini header pins    
7.	Access to Vusb, the 'raw' USB voltage source, and the 'pre-regulator' voltage Vx


All of these improvements are incorporated in the Orone-mini-S8J. The signal driving the User LED is on pin 33, next to pin 31. The DISC signal pad is on the standard 0.1" grid, but is interior to the board. Access to DISC enables the user to easily upload programs into an unprogrammed STM32F303, removing the need for any programming device (e.g. ST-LINK, USB-to-UART, or JTAG).

Vusb and Vx are on the bottom header row, and are not part of the Maple-mini compatible pins. These new voltages should only be used if you understand what you are doing. Vusb in particular is not fully protected, and connects to the host PCs USB socket. The pads are not labelled on top partly due to lack of space, and partly to avoid giving the impression that these are 'easy-to-use' signals.
 
The idea goal is to enable anyone stacking a daughterboard, to use the extra signals and voltages. Putting the pads on a 0.1" grid supports the use of simple daughterboard technology like matrix board, or strip board (e.g. Veroboard).

Maple-mini uses very small components in order to achieve its 0.6" pin-header spacing. They are unsuitable for most makers, and part of the goal of Orone-mini is to be DIY freiendly. Also one of those Maple-mini components is expensive and difficult to source, C1, the power supply smoothing capacitor, which is a 1206 case size. Orone-mini replaces C1 with a larger, lower cost, 2917 (7343 Metric) case size. 
