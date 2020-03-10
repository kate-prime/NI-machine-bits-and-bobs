# NI-machine-bits-and-bobs
Playback and recording codes for the big flight room

Simple Delay Line user manual:
KA 2020

This does what it says on the tin. A bare bones vi for loading and triggering playbacks of premade stimuli.

Stimuli:
Stims should be a .mat file with each stimulus as a separate cell in a structure. The scale for the display was set with a 250k sampling rate in mind, but other rates will probably not break anything. The file path for the stimulus is inputtable. Before starting the vi, select the stimuli (by number) that you want to include in this trial (min=1, max=as much as the memory can hold, but hasn't been stress tested)

Speaker considerations:
vi includes a step for applying a calibrated IR (impulse response) filter. Figure out which speaker you are using and if there is a file for it. This step can be commented out in the matlab node, but it is not advised. Likewise, the amplitude of playback can be changed, but this should be checked and calibrated for each speaker.

Analog Input:
Warning: analog input is not infinitely continuous. it will time out after 20 minutes, so remember to restart the vi periodically.
Input Channel ai1
Trigger level: 1v, but can be changed to adjust sensitivity:noise tolerance
Tigger window: 250 samples (1ms) before and 1000 (4ms) after trigger threshold is met

Analog Output:
output channel: ao2
set for a 250k sampling rate, so remember to change if yours is different

Delay:
still in testing to find absolute minimum delay, but ~4ms would be as low as I trust.
