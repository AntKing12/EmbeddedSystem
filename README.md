# EmbeddedSysyem
Embedded Systems code used through the coarse

Created a matlab  file that allowed for a filter and signal to be created
The signal would be run at different frequencies to test how the filter would react to different signals

The filter was made using the butter function in matlab.
It was decided to be a second order system with a breakfreqency of 7500hz
The b and a coefficents were then taken from the matlab model and used to make a filter in code using difference equations

For ease of use the existing code "Analog pass through Systik" was used to allow for use of the systick interupt and the DAC/ADC fuctions rather then reqriting them

