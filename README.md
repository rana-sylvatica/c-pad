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

### How it works

The c-pad PCB converts digital button presses to voltage levels that correspond to appropriate analog values using a resistor network (schematic below)

![image](https://user-images.githubusercontent.com/95242582/230264027-c07d42f8-15de-4f2c-8555-aef481b29d64.png)

The raw output from the c-pad at each of the cardinals and diagonals can be visualized with the plot below

![image](https://user-images.githubusercontent.com/95242582/230263892-518bc74b-3cef-48cc-94a1-3a5296bef9e5.png)

You may note that the upper left and lower right diagonals fall well outside the unit circle.  This is not a problem, as the values are normalized by the controller to sit at the edge of the unit circle.

### Components

The following components are required to make a c-pad module:
- 1x PCB
- 1x center insert (cpad_core in the files)
- 4x button
- 1x screw (
- 1x 

### How to assemble


### How to install



### Future work?

Here are some ideas for things that would be cool to see as continuations of this project:

 - A c-pad for a Hori GCC
 - A c-pad for a Switch Pro Controller
 - Additional button(s) as angle modifiers (or a PhobGCC firmware version that reuses either X/Y as a c-pad angle modifier maybe?)
 - An improved GCC d-pad using a design similar to the c-pad
 - A version of the c-pad for the GCC left analog stick (this would be pretty silly but might be good for platformers?)
