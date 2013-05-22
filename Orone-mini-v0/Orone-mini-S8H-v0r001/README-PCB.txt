Orone-mini-S8H-v0r001
Copyright 2013 G Bulmer

This work is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.
I ask that my name remain visible in the copper.

The pin headers are standard 'breadboard friendly' 0.1" pitch.
The two rows of pin headers are 0.8" apart, and hence fit a single breadboard.
The board is 2.4" long x 1" high. Most components are 1206 or larger.

1206 components are too big to fit in mini 2.1" length. 
Further 8mil track/8mil clearance required more board area
Hence the board is lengthened from 2.1" to 2.4"
Maple-mini's 1206 C1 is replaced with 7343-case size to reduce component cost

Design Rules: OSHPark.com & Seeedstudio 'Fusion' PCB Service

Routing
8mil track 8mil space, or larger, to enable a wider range of PCB manufacturers to reliably make the board.
Tracks from thru-hole (hand soldered) components, except pin headers, are 10mil or wider. This is intended to make the tracks more robust.

All Bottom Layer tracks are 10mil or bigger, except Crystal tracks; this is intended to be easier to make reliably.

Vias: The three via shapes are used to give information, and help 'read' the PCB.
VIA KEY
ROUND:   Signal
OCTAGON: Power (e.g. Vcc) Digitil Ground or segregated Ground (e.g. AGND) vias
SQUARE:  Digital Ground thermal vias, mainly for heat dissipation

Notes
There are four Hidden Airwires, which do not need routing (replicated on switches)
For safety, type 'RATSNEST *' to make them visible before making any changes
Two pads 33 and DISC, printed at 45 degrees, are signals, not for components.
DRC->Restring Pads & Vias minimum increased from OSHPark 7mil to 10mil to support more PCB manufacturers design rules by providing larger annular rings.

Ventosus found the ADC on Orone-mini-S8A was 'noisier' than Maple-mini. So the ADC tracks are more thoroughly separated from other tracks.
