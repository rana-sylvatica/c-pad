# c-pad
simple modkit to turn GameCube controller c-stick into 4 digital directional buttons

![FsV6db5XgAEQ6om](https://user-images.githubusercontent.com/95242582/230263397-5fa1a9be-560e-4d4e-80cc-204167917ca0.jpg)

### Overview

This repository contains the following design files:
 - 3D models of the c-pad center insert and buttons, both as individual components and panelized for ordering from a 3D printing service
 - KiCad PCB design files for both the OEM/Phob1.X and Phob2.0 versions of the project
 - PCB fabrication files (Gerber, BOM, CPL) for both the OEM/Phob1.X and Phob2.0 versions of the project

### Licensing

This project is licensed under CERN Open Hardware Licence Version 2 - Strongly Reciprocal

In short, this means:
 - License applies to publicly available hardware designs
 - Allows use, reproduction, modification, distribution, and sale of the design
 - License requires distribution under same terms, attribution to original designer(s)
 - Does not grant trademark rights, includes disclaimer of liability
 - License may be terminated for non-compliance

Anyone may use these design files to make their own c-pad for personal use or to sell, or modify the design however they wish.
However, if a modified design is distributed (either digitally or physically beyond personal use), the modified design must be publically posted under the same terms.

### Compatibility

The c-pad design files here are split into two versions.  

One version is compatible with T3 OEM motherboards (and T1/T2 OEM motherboards with JST c-stick cables, but NOT T1/T2 that have soldered ribbon cables [different pinout]), and PhobGCC 1.X.  May also be compatible with Goomwave (untested as of yet).  This version has a 4-pin cable header on the PCB.

The other version is compatible with PhobGCC 2.0 boards.  This version has a 6-pin cable header on the PCB.

### How it works

The c-pad PCB converts digital button presses to voltage levels that correspond to appropriate analog values using a resistor network (schematic below)

![image](https://user-images.githubusercontent.com/95242582/230264027-c07d42f8-15de-4f2c-8555-aef481b29d64.png)

The raw output from the c-pad at each of the cardinals and diagonals can be visualized with the plot below

![image](https://user-images.githubusercontent.com/95242582/230263892-518bc74b-3cef-48cc-94a1-3a5296bef9e5.png)

You may note that the upper left and lower right diagonals fall well outside the unit circle.  This is not a problem, as the values are normalized by the controller to sit at the edge of the unit circle.

### Components

The following components are required to make a c-pad module:
- 1x PCB
- 1x c-pad core
- 4x c-pad button
- 1x screw (https://www.mcmaster.com/97349A413/ - there's probably other similar screws on Amazon/AliExpress/etc that would work)
- 1x ribbon cable (https://kadano.biz/phobgcc-2-0-c-stick-ribbon-cables-6pin/ - can also use individual wires but is more difficult.  If making for OEM/Phob1.X and only 6-pin ribbon cables are available, just cut off two of the wires to make a 4-pin cable)

Resin 3D printing is the best way to manufacture the c-pad core.  Black Resin from JLCPCB (not Imagine Black - this is confusing as JLC recently added a 2nd black resin option) is my favorite for this.  Consumer-grade MSLA printers also do a nice job in my experience.

The c-pad buttons can be manufactured with resin printing, SLS/MJF nylon printing, or resin casting

SLS printing in white PA12 and dyeing with RIT dye is a nice way to get durable, vibrant, cheap buttons.  I use https://www.jawstec.com/ for this.

![FrWmiTQWwAI0IbI](https://user-images.githubusercontent.com/95242582/230267061-c33eb53b-f4a8-41f7-abc7-e3f1ae287048.jpg)

### How to assemble

Assembly is very simple:
 - put the buttons in the core
 - put together the PCB and core such that the alignment pegs line up and the slots in the core that mate with the GCC shell ribs are pointing "down" and "in" as seen from the perspective of someone holding the GCC (see image below).

![IMG20230404185115](https://user-images.githubusercontent.com/95242582/230266436-d84cf887-699b-408d-a1c6-2d527fa0cb17.jpg)

### How to install

Installation is also simple:
 - desolder the existing cstick cable from the GCC motherboard
 - solder in the new cable 
 - solder the other end of the new cable to the c-pad PCB
 - put back in shell
 - should look like the image below
 
![FsV6dreWIAUIO0w](https://user-images.githubusercontent.com/95242582/230266667-c7480798-2123-4ec5-b0c6-69174c922d44.jpg)


### Future work?

Here are some ideas for things that would be cool to see as continuations of this project:

 - A c-pad for a Hori GCC
 - A c-pad for a Switch Pro Controller
 - Additional button(s) as angle modifiers (or a PhobGCC firmware version that reuses either X/Y as a c-pad angle modifier maybe?)
 - An improved GCC d-pad using a design similar to the c-pad
 - A version of the c-pad for the GCC left analog stick (this would be pretty silly but might be good for platformers?)
