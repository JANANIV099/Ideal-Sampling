# Ideal-Sampling
## Aim:
  -  To perform ideal sampling and observe the sampled signal waveform.
## Tools required:
 - python colab.
    
## Program:
~~~~
import numpy as np

import matplotlib.pyplot as plt

from scipy.signal import resample

fs = 100

t = np.arange(0, 1, 1/fs)

f = 5

signal = np.sin(2 * np.pi * f * t)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal')

plt.title('Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

t_sampled = np.arange(0, 1, 1/fs)

signal_sampled = np.sin(2 * np.pi * f * t_sampled)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')

plt.title('Sampling of Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

reconstructed_signal = resample(signal_sampled, len(t))

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')

plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()
~~~~
## Output Waveform:
   ![ideal](https://github.com/user-attachments/assets/6660c479-7c2f-423c-96ae-5873ab73751a)
   ![ideal 2](https://github.com/user-attachments/assets/7c3c0b9f-3c1a-4982-9928-5f8ffe5a7940)
   ![ideal 3](https://github.com/user-attachments/assets/8f7dd7a1-eba5-4007-b4f6-3a6f8313a497)

## Results:
  - The continuous sinusoidal signal was successfully sampled using ideal (impulse) sampling.
     

