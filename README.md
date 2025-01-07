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
files, WAVE files, etc used in the VST will NOT BE AVAILABLE
from within the DAW at startup or its presets. 

MD2 PRESETS
The best way to use MD2 is to load and save presets within the VST.
The preset files save any custom IR data in them.

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

There are 20 programmed IRs built in to the VST. External IRs can be loaded
by selecting IR 20 or using the LOAD IR button. Loaded IRs can be resampled.
The VOICE option mixes the IR with a full frequency IR. So only brightness
can be added.

DELAY AND REVERB BLOCKS<br/>
These effects are fixed at these positions. The effects are always "ON".
To bypass the effect set its MIX value to 0 (zero).

OUTPUT BLOCK<br/>
The final block has controls for balance, stereo effect, and output filters. 
The stereo effect (WIDTH) will delay either the left or right channel to
create stereo. 

STEREO/MONO SIGNAL PATH 
------------------------------------------------------------------
The IR calculations are very CPU intensive. This means the best mode
to operate in is MONO. This is the default mode. In this mode the signal 
on the top row of the VST diagram is mono from input to IR. The signal 
is stereo after the IR. If a stereo modulation effect is desired, place
it after the amplifier block.

When running in STEREO mode, the entire VST is in stereo. This is very CPU
intensive. There can be up to four IRs being calculated at one time. One
for input EQ and one for Speaker sim on both left and right channels. This is
1000's of calculations for each sample of the audio data.


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

TIPS AND TRICKS<br/>
Thump and Air are very useful. They are useful for most gain settings.

Sag is best used on low gain amps to soften crunch. It will reduce clarity 
on high gain amps. Best to turn it off for high gain.

Thin reduces overall gain. Its main goal is to reduce swirling ghost notes
caused by the VST having more gain that tubes are capable of doing. So thin 
is best used for super high gain amps while soloing. 


PEDAL BLOCK
------------------------------------------------------------------
There are 20 pedals programmed into the VST. Most have limited use cases.
The most important are the OverDrives and the DIST EQ pedals. These will 
let you adjust your guitar sound going into the amplifier section. Which
may be required to get the best possible sound.


MODULATION BLOCK
------------------------------------------------------------------
TYPICAL MOD EFFECTS
There are standard style effects available here like Chorus, phaser,
flanger, etc. There are also some chorus based effects that create
pitch based sounds. There are four mono-synthesizer styled effects
available also. Three of these effects require specific WAVE files
to operate. 

IMPULSE RESPONSES
------------------------------------------------------------------



















