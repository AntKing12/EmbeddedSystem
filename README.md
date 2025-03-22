# Getting started with embedded systems project

## Matlab
Created a matlab  file that allowed for a filter and signal to be created
The signal would be run at different frequencies to test how the filter would react to different signals

The filter was made using the butter function in matlab.
It was decided to be a second order system with a breakfreqency of 7500hz
The b and a coefficents were then taken from the matlab model and used to make a filter in code using difference equations

For ease of use the existing code "Analog pass through Systik" was used to allow for use of the systick interupt and the DAC/ADC fuctions rather then rewriting them

## Filter Function

![image](https://github.com/user-attachments/assets/34952c4e-3701-4905-b192-ded071ac9886)

![Screenshot 2025-03-22 153510](https://github.com/user-attachments/assets/2820b059-3966-4d76-a4c2-d208965e6768)

Using the difference equation the output can easily be calculated
The b and a coeffcients are stored in arrays which remain unchanged 
x and y are rotated as new information in brought in to allow for use in the equation


## Port issue
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

## Results
Testing was done using oscilliscopes and comparing the output of the filter to the matlab model to view if the real world results matched expected values.
### Sine wave input
#### 200hz
<img src="https://github.com/user-attachments/assets/74140883-4965-469e-bb5a-e402e2281356" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/b760b9ac-640e-4411-952f-20b69b66a8cd" alt="200hz sin" width="400" height="300">

#### 3000hz
<img src="https://github.com/user-attachments/assets/5d56a05d-b9f7-4bab-9f72-a4ddf948c17c" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/4467433a-c3e3-4490-8680-bdd46c48d49b" alt="200hz sin" width="400" height="300">

#### 7500hz
<img src="https://github.com/user-attachments/assets/fb7171ec-423d-45fd-b645-c9b81e24b1c3" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/fb63e6f8-f5e0-425c-af71-da7c83489a56" alt="200hz sin" width="400" height="300">

#### 30000hz
<img src="https://github.com/user-attachments/assets/8d88d68a-72e3-4823-bc3a-1864000cc694" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/a4128e41-e7a8-4ac5-a40c-e4cb69b0d540" alt="200hz sin" width="400" height="300">

### Square wave input

#### 200hz
<img src="https://github.com/user-attachments/assets/9158efab-5920-47d1-8470-fe2042c9ea22" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/81ace64d-d1ea-4dd0-86d9-4b455247dd5d" alt="200hz sin" width="400" height="300">

#### 2000hz
<img src="https://github.com/user-attachments/assets/e2edb72d-b7b0-459f-947e-15a603c89497" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/b833e632-36cd-493b-b53c-95419a001da4" alt="200hz sin" width="400" height="300">


#### 7500hz
<img src="https://github.com/user-attachments/assets/a7810ef4-8ecf-47eb-b458-22a3aa488239" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/f92557a0-1982-4439-a2b4-b019f60f1934" alt="200hz sin" width="400" height="300">

#### 20000hz
<img src="https://github.com/user-attachments/assets/83b37305-81a8-4520-98d2-aa6961712c2c" alt="200hz sin" width="400" height="300"> <img src="https://github.com/user-attachments/assets/67deacc3-7bdb-40ff-ba47-e4201a4e94e2" alt="200hz sin" width="400" height="300">
