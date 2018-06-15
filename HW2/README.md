# HW2 Signal Analysis

Download and install GNU Octave from https://www.gnu.org/software/octave/

Run the following code in Octave.

```
clear;
Fs = 44100;
t = 0:1/Fs:0.4-1/Fs;
harmonics = [1.0, 0.399064778, 0.229404484, 0.151836061,0.196754229, 0.093742264, 0.060871957,0.138605419, 0.010535002, 0.071021868,0.029954614, 0.051299684, 0.055948288,0.066208224, 0.010067391, 0.00753679,0.008196947, 0.012955577, 0.007316738,0.006216476, 0.005116215, 0.006243983,0.002860679, 0.002558108, 0.0, 0.001650392];
pitches = [261.63;293.66;329.63;349.23;392.00;440.00;493.88;523.25];
notes = [];
composite_inc = [];
composite_dec = [];
for(i=1:length(pitches))
    sil = zeros(1,length(t)/2);
    wav = zeros(1,length(t));
    for(h=1:length(harmonics))
        wav = wav + harmonics(h)*sin(2*pi*h*pitches(i)*t);  
    end;
    notes(i,:) = wav.*hanning(length(wav))';
    composite_inc = [composite_inc,notes(i,:),sil];
    composite_dec = [notes(i,:),sil,composite_dec];      
end;
soundsc([composite_inc,composite_dec],Fs);
```

1) Explain what each statement does. Note that we assume the unit of t to be "second" and Fs to be "Hz".

2) How many frequency components are there in each of the note constructed from the code? 

3) Plot the waveform of the first 3 cycles of the 3rd note. The x-axis must be in "second". (See: help plot)

4) Compute and plot (the magnitude of) the DFT of the 3rd note (only the 3rd note). The x-axis must be in "Hz". Scale the plot so that the spectrum ranges from 0 to Fs/2. (See: help fft, help abs)

5) Discuss the spectrum whether the harmonics are at the expected frequencies.

6) Create an M-file that, when executes, it composes a short tune (E.g.: The hook of your favorite song) into a WAV file (See: help audiowrite). You can learn how to create an m file by watching "Octave Tutorial 06 - M-Files" YouTube video by Paul Nissenson

When your work is graded, the M-file will be executed as-is and we expect it to produce the same WAV file.
