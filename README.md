# ZX-Videoface


This is a clone of the Romantic Robot Videoface clone [(link)](https://spectrumcomputing.co.uk/entry/12523/ZX-Spectrum/Romantic_Robot_Videoface) for the ZX128 Spectrum RC2104 board [(link)](https://github.com/ZXQuirkafleeg/ZX128).

Notable features are:
*	Composite video input
* Monochrome scanning of 4 frames per second at a resolution of 256 by 192 pixels
* Video level control 


![Videoface clone](https://github.com/ZXQuirkafleeg/ZX-Videoface/blob/main/Images/Videoface%20V1.1%20-%20front.jpg)

## Design

The Videoface design is both impressive and clunky.  A description of the circuit can be found [here](http://www.ep128.hu/Sp_Hardware/SP_Videoface.htm) and schematics [here](https://github.com/ZXQuirkafleeg/ZX-Videoface/tree/main/Description).  Address decoding is partial so other perhipherals may well conflict.

For the RC2014 implementation, a few minor changes have been made.  74HC devices have been used and unused inputs are either tied high or low to be inactive.  Decoupling capacitors have also been added.

## Software

The Spectrum Videoface software is [here](https://github.com/ZXQuirkafleeg/ZX-Videoface/tree/main/Software) and the manual [here](https://github.com/ZXQuirkafleeg/ZX-Videoface/blob/main/Manual/Videoface_Manual.txt)

## Build
All components are though-hole and standard density.  A schematic can be found [here](https://github.com/ZXQuirkafleeg/ZX-Videoface/blob/main/PCB/ZX%20Videoface%20-%20Schematic%20-%20V1.1.pdf) and BOM here [here](https://github.com/ZXQuirkafleeg/ZX-Videoface/blob/main/PCB/BOM%20-%20Videoface%20-%20V1.1.csv).

### PCB

For the PCB, EasyEDA (V6.5.22) design files can be found [here](https://github.com/ZXQuirkafleeg/ZX-Videoface/tree/main/PCB) and gerbers [here](https://github.com/ZXQuirkafleeg/ZX-Videoface/blob/main/PCB/Gerber_PCB%20-%20RC2014%20-%20Videoface%20-%20V1.1.zip).  The PCB is a standard two layer board approx. 100mm by 80mm.  

### Clock generator

The Videoface dot clock is a simple RC schmitt trigger oscillator using U7.  Pin 3 of U7 should be ~12.5 MHz.  You may need to change the value of C16 a little accordingly.

## Jumpers and Connectors

* J1 – RC2014 Bus connector
* J2 – External composite video source (e.g. PAL camera)
* CN1 - Alternative external  video source

## System Test

Install the CPU, ZX128 and Videoface boards in the backplane.  Load the Videoface software and connect a PAL source - the green 'Sync' led should light.  Starting capture on the software will turn on the 'Scan' led.  Adjust R9 to set the black/white threshold.  Additional current draw should be <50 mA.
