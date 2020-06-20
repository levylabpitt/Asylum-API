# Asylum AFM APIs
 A LabVIEW wrapper for Asylum AFMs
 Note: The developers of this repository are not associated with Oxford Instruments or Asylum Instruments. 
 This API is intended for use with the Asylum Cypher and the Asylum MFP-3D atomic force microscopes. This software is provided as is.
## How to use:
### Getting Started
Before you begin, if you use a command, make sure you understand the implications of said command. Furthermore, you should also check over the syntax of any commands that are sent to an instrument. Do not use this API if you are unwilling to review the commands that are being sent to the instrument prior to using this API. I have added a Debug Mode to this API to facilitate checking over the commands sent to the instrument. I have tried to ensure that any commands sent do not have any grammatical mistakes through unit tests, but at the end of the day it is up to the instrument user to do so before attempting to use any of these commands.

Now that I got that out of the way, lets run through a simple command that only interacts with the command software, not the instrument itself. First we need to get a refernece to the Igor Pro Software. Place the Asylum_OpenRefnum.vi onto the block diagram. For now, lets not put the API into debug mode. Next, place the Asylum_CloseRefnum.vi onto the block diagram. This needs to be called for every time that you open a reference. Note that the debug mode can only be overwritten by the Asylum_OpenRefnum.vi. 

Now that we have the functionality to open and close the reference to the Igor Pro Software, let's get the XOP version of the software. This does not interact with the instrument, so it is a good first command to send with very little consequence. You can try this command using the command panel in the Asylum Igor Pro Software. The command that we generate in LabVIEW is the same as typing `print td_XopVersion()` in the command panel. All that we have added is some functionality to return the value to LabVIEW. So once you understand what is going on, lets place the function Asylum_XOPVersion.vi onto the block diagram. You want to wire the reference from 
Asylum_OpenRefnum.vi into Asylum_XOPVersion.vi, and wire the output reference from Asylum_XOPVersion.vi into Asylum_CloseRefnum.vi, like so:
![Basic Example](/resource/ExampleUse.png)



## Contact
joe.albro@levylab.org
## License
This is licensed under a BSD 3 clause license.
