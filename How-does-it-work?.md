The **KunaiGC** is as an IPL-Replacement for the Gamecube.

--- *But what is the IPL and why do one want to replace it?*

IPL stands for (**I**)itial (**P**)rogram (**L**)oader and it is the first program the Gamecube starts on it's bootup.

With an IPL replacement we can decide what the Gamecube starts on bootup. This could be Swiss or any other .dol-File.

--- *How does **KunaiGC** does all of that?*

With an **KunaiGC** installed the Gamecube asks the KunaiGC what to do:
- If the **KunaiGC** is active the KunaiGC loads it's contents from it's Flash e.g. Swiss directly.
- If the **KunaiGC** is inactive the KunaiGC is turned of and the stock Gamecube IPL is used.

*More technically?:*
The Gamecubes CPU sends it's normal IPL boot-commands to the IPL-Chip. 
Since the KunaiGC is hooked onto it, the KunaiGC grabs this request from the CPU, before the IPL get's it and the CPLD on the KunaiGC decides, which data-path to choose. 

- If the KunaiGC is active the KunaiGC starts it's loading procedure with the KunaiLoader, which is stored on the flash.
- If the KunaiGC is inactive the CPLD on the KunaiGC sends the CPU requests directly to the stock IPL.



*******