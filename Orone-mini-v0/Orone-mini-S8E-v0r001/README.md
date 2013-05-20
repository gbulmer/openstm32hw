Orone-mini-S8E-v0r001
=====================

Maple-mini compatible STM32F development board. 

This board has not been made and tested yet. It is being released now to gather feedback, and hopefully encourage people to test it. The board has been designed for manufacture using two PCB makers. However, a goal is to ensure it is manufacturable by a wider range of PCB makers, so please feedback.

This is board designed to be DIY-assemblable, but otherwise software and signal compatible with Maple-mini. It has been inspired by some of Siy's mini48 innovations, and also the availability of STM32F303 in 48pin LQFP packages.

It is a breadboard-friendly form-factor; all pins are on breadboard 0.1" grid. Unlike Maple-mini, the two 20pin 0.1" headers are 0.8", and not 0.6" apart. However it is still narrow and short enough to fit into single breadboards.

Maple-mini C1 1206-case-size has been replaced by a 2917 (7343 Metric) case size. 
Orone-mini-S8E brings two extra signals, and two extra voltages to pads compared to Maple-mini. One signal (for the LED) and the two voltages are on the headers 0.1" grid. The USB 'DISC' signal is paired with a Ground pad, 0.1" away, enabling DISC to be shorted to ground with a jumper using a 2x0.1" header.


Maple-mini improvements
-----------------------
LeafLabs Maple-mini is a very impressive and useful Open Source Hardware development board. It offers approximately 4x more memory and CPU performance than an Arduino UNO, much improved peripherals, and about 50% more I/O pins in a tiny package that fits into a 40pin DIL IC socket. It is supported by an Open Source IDE and library similar to the Arduino UNO. 

However there are areas that can be improved:  
1.	DIY-assemblable; this is outlined below  
2.	Robust operation above 6V while providing current to e.g. LEDs and electronics  
3.	USB Electro-static Discharge (ESD) protecting the Host PC and Orone-mini  
4.	Socket for easier-to-connect external power  
5.	Power-on indicator  
6.	Reduced-cost of capacitor C1 by using larger size (2917/7343)  
7.	Access to all STM32F signals; two are not connected to header pins  
8.	Access to the USB input voltage (after polyfuse protection)  
9.	Access to diode-protected but unregulated input voltage  
10.	USB 'DISC' signal on 2 x 0.1" header to simplify STM32F303 USB boot


All of these improvements are incorporated in the Orone-mini-S8E. The signal driving the User LED (pin 33) is on a pad next to 31. The DISC signal pad is harder to access. It is not on the standard 0.1" grid, and is interior to the board. The aim is to enable anyone stacking a daughterboard, to use the extra two signals. Putting signal 33 pad on a 0.1" grid supports the use of simple daughterboard technology like matrix board, or strip board (e.g. Veroboard).

Maple-mini uses very small components in order to achieve its 0.6" pin-header spacing. One of those components is expensive and difficult to source, C1, the power supply smoothing capacitor. Maple-mini uses a 1206 case size for C1. This has been replaced by a 2917 (7343 Metric) case size. 
