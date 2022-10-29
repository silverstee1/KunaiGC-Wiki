

First you need to get all the needed parts:

1.  Gamecube DOL-001
2.  KunaiGC You need to disassemble the Gamecube (easiest way how to do that: Look at  [iFixits-Guide](https://de.ifixit.com/Teardown/Nintendo+GameCube+Teardown/1727), how to do that)

Disassemble the Gamecube up to the heatsink and now stop for a second.

It's a bit tricky to get the heatsink off, since the thermal pads are most likely the original ones, that are a few years old.

First take of all the screws from the heatsink. 
Now turn on the gamecube for a few minutes, sothat the CPU and GPU are getting warm. This softens the thermal pads and you sould be able to get the heatsink of without much force and hopefully without tearing the pads in the process.

Now to the soldering:

With **KunaiGC** you **don't** need to life any pins on the IPL. 
So simply lay the QSB-Board over the IPL

![](https://github.com/KunaiGC/KunaiGC/blob/a6744ee455d6b89b1c49a5aaf6fcaeeba9615400/images/qsb.jpg)

and solder every castallation to the IPL Chip.

![](https://github.com/KunaiGC/KunaiGC/blob/a6744ee455d6b89b1c49a5aaf6fcaeeba9615400/images/qsb_soldered.jpg)

If you have trouble getting the solder stick to the IPL's chipleg and the castallation a good tip is to double up the pin with an componentleg e.g. and as always with soldering: Flux is your friend.

If you have trouble with the Crystal **"X2"** you can try to manouver it a few milimeters away from the qsb.

To check the soldering you can test at this points:

Now the heatsink can go back onto the CPU and GPU. Is should look like this:
![](https://github.com/KunaiGC/KunaiGC/blob/a6744ee455d6b89b1c49a5aaf6fcaeeba9615400/images/qsb_under_heatsink.jpg)
