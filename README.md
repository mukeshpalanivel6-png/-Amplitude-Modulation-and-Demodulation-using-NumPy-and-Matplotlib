# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

PROGRAM:
~~~
iSmport numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert
# Parameters
A_c = 1.0 # Carrier amplitude
f_c = 100 # Carrier frequency in Hz
f_m = 5 # Message frequency in Hz
A_m = 0.5 # Message amplitude
sampling_frequency = 1000 # Sampling frequency in Hz
duraƟon = 1 # DuraƟon of the signal in seconds
# Time axis
t = np.linspace(0, duraƟon, int(sampling_frequency * duraƟon))
# Message Signal
m_t = A_m * np.cos(2 * np.pi * f_m * t)
# Carrier Signal
c_t = A_c * np.cos(2 * np.pi * f_c * t)
# Amplitude ModulaƟon (AM) Signal
s_t = (1 + m_t) * c_t
# AM DemodulaƟon
# 1. Compute the analyƟc signal using the Hilbert transform
analyƟc_signal = hilbert(s_t)
# 2. Extract the envelope of the analyƟc signal
envelope = np.abs(analyƟc_signal)
# 3. Demodulate the signal by removing the DC offset and dividing by the carrier amplitude
demodulated_message = (envelope - A_c) / A_m
# Ploƫng the Results
plt.figure(figsize=(12, 10))
# Original Message Signal
plt.subplot(4, 1, 1)
plt.plot(t, m_t)
plt.Ɵtle('Original Message Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
# Carrier Signal
plt.subplot(4, 1, 2)
plt.plot(t, c_t)
plt.Ɵtle('Carrier Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
# Amplitude Modulated (AM) Signal
plt.subplot(4, 1, 3)
plt.plot(t, s_t)
plt.Ɵtle('Amplitude Modulated (AM) Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
# Demodulated Signal
plt.subplot(4, 1, 4)
plt.plot(t, demodulated_message)
plt.Ɵtle('Demodulated Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.Ɵght_layout()
plt.show()
~~~
 __Output__:
<img width="756" height="523" alt="image" src="https://github.com/user-attachments/assets/dda49653-4466-4ac3-82a7-52320bcc5b4c" />

CALCULATION:
![WhatsApp Image 2025-12-01 at 16 59 51_185970cb](https://github.com/user-attachments/assets/37c5be77-cc1b-4e47-bb93-6f57dacfbc6d)



 __Result__:
Thus amplitude modulation using python and matplotlib is done and verified

