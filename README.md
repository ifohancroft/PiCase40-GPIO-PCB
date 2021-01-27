# Pi Case 40 GPIO PCB

A replacement PCB for Pi Case 40, that fixes the reversed GPIO Issue.

**Not yet ready or tested**

 - The PCB has been made with KiCAD and is located under PiCase40/. It includes all the schematic symbols, footprints and 3D shapes it uses, in project-specific libraries, located under Library/
 - PCBReference.FCStd is a FreeCAD file containing the PCB outline and component placements, that can later be used as a reference, when creating the PCB outline and placing the components, in KiCAD. It is also the file, used to create the technical drawings.
 - Technical drawings showing the PCB dimensions, can be found under Images/

In-case you want to modify this PCB, or create a new one from scratch, there are certain important dimensions you must know about:

![PCB Dimensions](TechnicalDrawings/Dimensions.png)

As you can see, there are 4 different types of dimensions, marked in black, red, green and blue.

To make things easier to see, let's show each different type of dimensions on their own, when talking about them:

Black (Informative Dimentions): You can't really change those, as they show typical component sizes, however some other dimensions may depend on them.
![Informative PCB Dimensions](TechnicalDrawings/Dimensions-Informative.png)

 - H: Width and Depth of the body of a typical tactile switch.
 - D: Depth of the body of a typical pin header (both male and female)
 - C: Width of the body of a typical pin header (both male and female)
 - V: V is an exception, as it doesn't show a component's dimension, instead it shows how far the vertical center of the male header is, from the grid's 0,0. This is to help you center everything.

Red (Exact Dimensions): Dimensions that must be exactly as shown, or things won't fit.
![Exact PCB Dimensions](TechnicalDrawings/Dimensions-Exact.png)

## Modifying the PCB or creating a new from scratch

Whether you want to 

## TODO

0. Finish setting up the README
1. Update the PCB outline from the FreeCAD file.
2. Check component placement again.
3. Order a new PCB and hand solder it, to make sure it fits
4. Buy a Raspberry Pi to test the PCB?
5. Prettify the footprints
6. Figure out a way to make the PCB include the male header riser, so it can be factory assembled by the board house.
7. Update the README
