# Pi Case 40 GPIO PCB

A replacement PCB for Pi Case 40, that fixes the reversed GPIO Issue.

 - The PCB has been made with [KiCAD](https://kicad.org/) and is located under PiCase40/. It includes all the schematic symbols, footprints and 3D shapes it uses, in project-specific libraries, located under Library/
 - PCBReference.FCStd is a [FreeCAD](https://www.freecadweb.org/) file containing the PCB outline and component placements, that can later be used as a reference, when creating the PCB outline and placing the components in KiCAD. It is also the file, used to create the drawings for the [Tutorial](#Tutorial).
 - TutorialDrawings contains the images for the [Tutorial](#Tutorial)
 - A replacement GPIO sticker is located under Sticker/. sticker.svg is the source files, from it multi-sticker.svg is created by repeating the design and adding cut lines in-beteween. The green background is only for visibility while working and should be hidden before exporting. Finally, multi-sticker.png is the output file that should be used when creating an order. (Basically, the idea is that a single sticker is too small (height wise) for [StickerMule](https://www.stickermule.com/) to print. Also, I don't think their sticker sheets support transparent stickers, and they don't offer sample size purchases of them, but there is no need to pay €30 when all you need is one sticker. So, I created my own sticker sheet that can be ordered as one big transparent sticker and later cut to separate stickers.) 

## Placing an order

 - PCB: Instructions will be added later when it is finalized.
 - Sticker: (Keep in-mind I still haven't received my order, so the stickers are basically untested. The writing may be too small or too ugly. When this warning dissapears, you can count that they end up as I have intended them to)
  - Go to *https://www.stickermule.com/*
  - Click on *Stickers* in the menu at the top
  - Click *Clear Stickers*
  - Click *Order Samples*
  - Click *Order 10 clear stickers for $9* leaving the size to what it is.
  - Click *Choose file...* and select ***multi-sticker.png***
  - Click *Continue*
  - Click *Checkout*
  - Add or confirm your shipping and payment info and click *Place your order*
  - Confirm the design during the proof approval stage, if everything looks good
  - Cut on the inside of the black lines when you receive your stickers, not in the middle of them. I.e. there are meant to be no black lines in your final, cut stickers.
  - TA DA! You now basically have 100 stickers for $9.

## TODO

### PCB

1. Hand-solder the new PCB iteration when it and the components arrive, to make sure it all fits.
2. Buy a Raspberry Pi and a HAT to test the PCB?
3. Figure out a way to make the PCB include the male header riser, so it can be factory assembled by the board house.
4. Print a final and pretty version of the PCB adding the instructions used for that, to the README and mark the project as complete

### Sticker

1. Wait for the sticker to arrive and make sure it fits.

## Tutorial

In-case you want to modify this PCB, or create a new one from scratch, there are certain important dimensions you must know about:

![PCB Dimensions](TutorialDrawings/Dimensions.png)

As you can see, there are 4 different types of dimensions, marked in black, red, green and blue.

To make things easier to see, let's show each different type of dimensions on their own, when talking about them:

Black (Informative Dimentions) - You can't really change those, as they show typical component sizes, however some other dimensions may depend on them:
![Informative PCB Dimensions](TutorialDrawings/Dimensions-Informative.png)

 - H: Width and Depth of the body of a typical tactile switch.
 - D: Depth of the body of a typical pin header (both male and female)
 - C: Width of the body of a typical pin header (both male and female)
 - V: V is an exception, as it doesn't show a component's dimension, instead it shows how far the vertical center of the male header is, from the grid's 0,0. This is to help you center everything.

Red (Exact Dimensions) - Dimensions that must be exactly as shown, or things won't fit:
![Exact PCB Dimensions](TutorialDrawings/Dimensions-Exact.png)

 - B: Horizontal center to center distance of the mount holes - 58mm. Same as the center to center distance of the Raspberry Pi 4 mount holes and Pi 40 Case mount posts.
 - F: Horizontal center to center distance between the mount holes and the female pin header - 29mm.
 - I: Vertical center to center distance between the left mount hole and the tactile switch body - 7.5mm.
 - L: Vertical center to center distance between the tactile switch body and the top mount hole - 5mm.
 - K: Horizontal center to center distance between the tactile switch body and the top mount hole - 7mm.
 - G: Vertical center to center distance between the female and male pin headers - 7mm.

Blue (Restrictive Dimensions) - Dimensions that don't have to be as shown, but still have a limit as they depend on other dimentions and component placements:
![Restrictive PCB Dimensions](TutorialDrawings/Dimensions-Restrictive.png)

 - A: Main mount holes diameter - 4mm. Must be between 4mm (bottom case mount posts' inner diameter) and 6mm (bottom case mount posts' outer diameter), so the PCB rests on the the posts, but allows the raised lip around the screw holes to go through.
 - E: Female header center to bottom board edge - 5mm. Must be between 5mm (half the thickness of a typical female pin header (dimension D:) + about 2.5mm for its SMD pads and some wiggle room) and 7mm as the inner board wall is 7mm away.
 - J: Top mount post hole diameter - 3mm. Must be less than 6mm (top mount post diameter) and not less than 2.5mm (top mount post inner diameter/screw hole diameter), so the PCB rests on the post but allows for the screw to go through.
 - O: Right mount hole center to board edge above it - 3.5mm. Must be bigger than half of dimension A to allow for some lip around the whole and not more than 3.54mm as Raspberry Pi's PoE header starts 3.54mm above the right screw hole center
 - P: Space for Pi's PoE Header - 3mm. Must be at least 2.6mm as the Pi's PoE header is 5.2mm by 5.2mm square on the same vertical axis as the right mount hole, but small enough to allow some lip around the male header for traces.
 - R: Cosmetic board cutout width - 5mm. If you are going to have this cutout, it must be at least as big as dimension M and less than K - J / 2 to allow for some lip to the left of both the tactile switch body and the top screw hole.
 - U: Case radiator support clearance - 6mm. It must be more than half of J to allow for some lip around the screw hole and depending on the degrees of the angle, watch out for the radiator support. Same X axis as the mount hole, 7mm to the right from its center the radiator support is reaches the height at which the PCB is mounted.
 - S: Male header center to top board edge - 4.5mm. It must be more than half of D to allow for some lip around the header, but not more than 4.5mm as the radiator starts about 4.5mm above where the center of your male header would be.
 - N: Right mount hole center to right board edge - 4mm. It must be more than half of A, to allow for some lip around the screw hole, but not more than 4.95mm as the Pi's Ethernet port starts there. Warning: If not the same as M, it would shift your board's horizontal center, making it difficult to center the board and position components relative to the center, without you having to find the new one yourself.
 - M: Left mount center center to left board edge - 4mm. It must be more than half of A, to allow for some lip around the screw hole, but not more than 5mm as this is where the inside of the left case wall starts. Warning: If not the same as N, it would shift your board's horizontal center, making it difficult to center the board and position components relative to the center, without you having to find the new one yourself.

Green (Loose Dimensions) - Dimensions that you can set to whatever you like (within reason) as every board edge or Pi component that is tall enough to interfere, are at least a couple of cm away:
![Loose PCB Dimensions](TutorialDrawings/Dimensions-Loose.png)

 - Q: Button center to top board edge - 5.5mm. As long as it's big enough to leave some lip around the switch body for its SMD pads, you can have it couple of cm if you like.
 - T: Top mount hole center to top board edge - 2.5mm. As long as you leave some lip around the hole, you can have it couple of cm if you want, but if you have the slanted edge on the right, keep in mind U.

All corners are 135 degrees, and the length of all of them except for the two on top around the top mount hole is 1.5mm.
