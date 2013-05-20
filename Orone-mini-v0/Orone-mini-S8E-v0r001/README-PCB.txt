Orone-mini-S8E-v0r001
Copyright 2013 G Bulmer

This work is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.
I ask that my name remain visible in the copper.

The pin headers are standard 'breadboard friendly' 0.1" pitch.
The two rows of pin headers are 0.8" apart, and hence fit a single breadboard.
The board is 2.3" long x 1" high. Most components are 1206 or larger.

1206 components are too big to fit in mini-like 2.1" length
Hence the board is lengthened from 2.1" to 2.3"
Replaced C1 with 7343-case size

Design Rules: OSHPark.com & Seeedstudio 'Fusion' PCB Service

Routing
Crystal tracks & Top Layer MCU tracks are 6mil/6mil in order to make enough space for components and isolation.
All tracks from thru-hole (hand soldered) components, except pin headers, are 10mil or wider. This is intended to make the tracks more robust.

All Bottom Layer tracks are 10mil or bigger, except Crystal tracks; this is intended to be easier to make.

Copper pours have 10mil isolation; this is intended to be easier to make.

Vias: The three via shapes are used to give information, and help 'read' the PCB.
VIA KEY
SQUARE:  Digital Ground (DGND) and thermal vias
ROUND:   Signal
OCTAGON: Power (e.g. Vcc) or segregated Ground (e.g. AGND)

Notes
There are four Hidden Airwires, which do not need routing (replicated on switches)
For safety, type 'RATSNEST *' to make them visible before making any changes
Labels for three pads, 33, DISC and GND, printed at 45 degrees, are not for components though they are sized for pins or headers.
DRC->Restring Pads & Vias minimum increased from OSHPark 7mil to 10mil to support more PCB manufacturers design rules by providing larger annular rings.
