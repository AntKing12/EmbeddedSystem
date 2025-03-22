# Getting started with embedded systems project

# Matlab
Created a matlab  file that allowed for a filter and signal to be created
The signal would be run at different frequencies to test how the filter would react to different signals

The filter was made using the butter function in matlab.
It was decided to be a second order system with a breakfreqency of 7500hz
The b and a coefficents were then taken from the matlab model and used to make a filter in code using difference equations

For ease of use the existing code "Analog pass through Systik" was used to allow for use of the systick interupt and the DAC/ADC fuctions rather then rewriting them

# Filter Function

![image](https://github.com/user-attachments/assets/34952c4e-3701-4905-b192-ded071ac9886)

![Screenshot 2025-03-22 153510](https://github.com/user-attachments/assets/2820b059-3966-4d76-a4c2-d208965e6768)





While working on the code an issue became apprent as no output was being read on the pa_0 the output port
Testing ahd to be done to see where the error was occuring
A constant was applied to the dac to see if an output was read
Changing the constant changed the value read on the oscilloscope showing that the DAC was working an outputting
The oscilloscope read that a signal was applied to the input showing the function generator worked as expected
The orignal analog pass through systik code was uploaded onto the L432kc to ensure that the changes to the code weren't affecting the pass through
The orignal code still did not work.
By changing the code to use pa_1 which has a ADC on channel 6 rather then chanel 5 to determine if pa_0 was broken.
A signal was then observed passing through the microprocessor
This change was passed onto the filtering code and the signal was now filtering correctly confirming that pa_0 was not reading a signal.

