# SSB-SC-AM-MODULATOR-AND-DEMODULATOR
## AIM

To write a program to perform SSBSC modulation and demodulation using SCI LAB and study its spectral characteristics
## EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

Note: Keep all the switch faults in off position

## ALGORITHM
  1.	Define Parameters:
     
    •	Fs: Sampling frequency.
    •	T: Duration of the signal.
    •	Fc: Carrier frequency.
    •	Fm: Frequency of the message signal.
    •	Amplitude: Maximum amplitude of the message signal.
    
  2.	Generate Signals:
     
    •	Message Signal: The baseband signal that will be modulated.
    •	Carrier Signal: A high-frequency signal used for modulation.
    •	Analytic Signal: Constructed using the Hilbert transform to get the in-phase and quadrature components.

  3.	SSBSC Modulation:
     
    •	Modulated Signal: Create the SSBSC signal using the in-phase and quadrature components, modulated by the carrier.

  4.	SSBSC Demodulation:
     
    •	Mixing: Multiply the SSBSC signal with the carrier to retrieve the message signal.
    •	Low-pass Filtering: Apply a low-pass filter to remove high-frequency components and recover the original message signal.

  5.	Visualization:
     
    Plot the message signal, carrier signal, SSBSC modulated signal, and the recovered signal after demodulation.

## PROCEDURE

  •	Refer Algorithms and write code for the experiment.
  
  •	Open SCILAB in System
  
  •	Type your code in New Editor
  
  •	Save the file
   
  •	Execute the code
  
  •	If any Error, correct it in code and execute again
  
  •	Verify the generated waveform using Tabulation and Model Waveform
## MODEL GRAPH
<img width="747" height="338" alt="image" src="https://github.com/user-attachments/assets/dd117c5d-ee32-47c7-946c-df6180b0d33f" />

## PROGRAM
Am = 7;
Ac = 14;
fm = 653;
fc = 6530;
fs = 653000;
t = 0:1/fs:2/fm;
m1 = Am * cos(2 * 3.14 * fm * t);
subplot(5,1,1);
plot(t, m1, 'b');
title('Message Signal');
xlabel('Time (s)');
ylabel('Amplitude');
c1 = Ac * cos(2 * 3.14 * fc * t);
subplot(5,1,2);
plot(t, c1, 'r');
title('Carrier Signal');
xlabel('Time (s)');
ylabel('Amplitude');
m2 = Am * cos(3.14/2 - (2 * 3.14 * fm * t));
c2 = Ac * cos(3.14/2 - (2 * 3.14 * fc * t));
s1 = c1 .* m1;
s2 = c2 .* m2;
lsb = s1 + s2;
usb = s1 - s2;
subplot(5,1,3);
plot(t, lsb, 'k');
title('Lower Sideband (LSB)');
xlabel('Time (s)');
ylabel('Amplitude');

subplot(5,1,4);
plot(t, usb, 'm');
title('Upper Sideband (USB)');
xlabel('Time (s)');
ylabel('Amplitude');
demod = abs(hilbert(lsb));
demod = demod - mean(demod);
subplot(5,1,5);
plot(t, demod, 'g');
title('Demodulated Signal');
xlabel('Time (s)');
ylabel('Amplitude');

## TABULATION
![WhatsApp Image 2025-11-18 at 19 24 27_8a947f5c](https://github.com/user-attachments/assets/a1461fe6-312a-497c-be4b-f4b5da0f8225)

## OUTPUT
<img width="710" height="577" alt="image" src="https://github.com/user-attachments/assets/83826e78-7708-45b2-b272-4c70e50b5f65" />

## RESULT
Thus, the SSB-SC-AM Modulation and Demodulation is experimentally done and the output is verified.

