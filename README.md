# Mako Distortion 2
* JUCE VST guitar processor.
* Tested on Windows only.
* Written in Visual C++ 2022.
* Version: 2.22
* Posted: January 7, 2024

VERSION
------------------------------------------------------------------
2.22 - Initial release.  
       
SUMMARY
------------------------------------------------------------------
A Juce/C++ VST3 guitar processor. Complete end to end processing
abilities like effects, amplifiers, EQ, etc.

THINGS TO KNOW
------------------------------------------------------------------
VST LIMITATIONS
VST's do not save strings variables. This means things like IR
files, WAVE files, etc used in the VST will not be available
from withint the DAW at startup or its presets. 

MD2 PRESETS
The best way to use MD2 is to load and save presets within the VST.
The preset files save IR data in them.

SIGNAL PATH
------------------------------------------------------------------
INPUT BLOCK
The guitar signal begins being processed at the INPUT block. It then
moves left to right on the VST diagram. The input block has settings
for high pass filter, Attack, and Noise Gate.

Attack is used for creating Pad/Violin effects and will gradually turn
the signal volume up after a silent moment in the playing. 

The Noise Gate turns the volume down while not playing. Adjust until
no noise is heard when not playing.

PEDAL BLOCKS<br/>
There are six possible pedal locations. These are used for things like
OverDrive, Distortion, and other gain based effects.

MODULATION BLOCKS<br/>
There are only two available mod effects that can be used at one time. 
These blocks can be located in three different locations: before amp,
after amp, or in the effect path of a reverb/delay block.

AMPLIFIER BLOCK<br/>
The amplifier has 31 possible channel settings. There are 30 amplifiers
and one bypass channel (0). 

IMPULSE RESPONSE (IR) BLOCK<br/>
An Impulse Response is a wave file the captures the frequency response
of a system. Here they represent the speaker being used by the amplifier
block. There are adjustements here for bass/treble balance (voice) and
resampling of the IR (Size).

DELAY AND REVERB BLOCKS<br/>
These effects are fixed at these positions. The effects are always "ON".
To bypass the effect set its MIX value to 0 (zero).
