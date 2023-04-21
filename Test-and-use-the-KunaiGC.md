# Bootsequences
<img src="https://github.com/KunaiGC/KunaiGC/blob/main/images/testusingkunai/Kunai_Controller_Manual_final.png" width=110% height=110%>  

To test the **KunaiGC** Features you can look at the boot process shown in the picture above. They are described in more detail below.

## Debugging Mode
By hold the D-Pad down on startup you'll get the debugging information as shown below:  
<img src="https://github.com/KunaiGC/KunaiGC/blob/main/images/testusingkunai/ddown.jpg" width=60% height=60%>

**At this moment you know, that the **KunaiGC** is soldered correctly and works as it should.**

## Boot directly into Swiss
Hold the Start-button on startup and you boot directly into an onboard Swiss-Version without any SD-Card needed:  
<img src="https://github.com/KunaiGC/KunaiGC/blob/main/images/testusingkunai/start_swiss.jpg" width=60% height=60%>

## KunaiRecovery
Hold the Z-button on startup and you boot into the KunaiRecovery. The **KunaiGC** can be de-/activated and the passthrough can be set here.  
<img src="https://github.com/KunaiGC/KunaiGC/blob/main/images/testusingkunai/zbutton.jpg" width=60% height=60%>

## Original and custom IPL
The **KunaiGC** starts the original IPL by default. But if you rename a dol-file you want to _ipl.dol_ and place it in the folder "KUNAIGC" on your SD-Card, the **KunaiGC** will boot automatically this program.
If you want to use Cubeboot just rename your _ipl.dol_ into _boot.dol_ and place the customized _cubeboot.dol_ into the KUNAIGC folder and rename it to _ipl.dol_.

## Remapping the buttons
Every button can be remapped to boot into an other program. Just rename the designated dol-files into one of the following and press its button on startup. Just place the dol-files into the root of your SD-Card. Even start and z can be remapped, but you cant enter the recovery or debugging mode as long these dol-files are present on the SD-Card.
The possible dol-files are:
* _a.dol_
* _b.dol_
* _x.dol_
* _y.dol_
* _z.dol_
* _start.dol_
* _left.dol_
* _right.dol_
* _up.dol_
<br/>

***

**Work is currently in progress to allow Swiss to communicate directly with the KunaiGC to load files onto the KunaiGC internal flash.**