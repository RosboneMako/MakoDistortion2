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
INPUT BLOCK<br/>
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

OUTPUT BLOCK<br/>
The final block has controls for balance, stereo effect, and output filters. 
The stereo effect (WIDTH) will delay either the left or right channel to
create stereo. 

AMPLIFIER BLOCK
------------------------------------------------------------------
The amplifier setion has 30 amps programmed. These amps can be adjusted
using the various controls. 

QUALITY<br/>
Each amplifier uses a 1024 sample IR for its frequency definition. IRs
are very CPU intensive. Changing the quality reduces CPU usage by using
a small section of the IR instead of the whole IR. 

THUMP, AIR, ASYM, POWER, SAG, and THIN<br/>
Thump and Air boost the low and high freqs using a distorting circuit.<br/>
Asymmetry adds distortion to the lower half of the signal only. <br/>
Power adds the same distortion across the full range. <br/>
Sag limits fast transients to simulate an amp running out of power.<br/>
Thin compresses the signal if a lot of gain is being used.<br/>

EQ MODE AND LOW PASS<br/>
There are 10 EQs prgrammed into the VST. Change EQs by changing the MODE
setting. The low pass is used to filter out harshness from any distortion
being used. 















