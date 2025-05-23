EXP NO:01 Ideal Sampling

Aim:
 To perform ideal sampling and observe the sampled signal waveform.

Tools required:
 python colab (for simulation)
 
Program:
~~~
import numpy as np
import matplotlib.pyplot as plt

t = np.arange(0, 1, 0.001) 
fm = 5 
fs = 20 

x = np.sin(2 * np.pi * fm * t)

n = np.arange(0, 1, 1/fs)  
xn = np.sin(2 * np.pi * fm * n) 

plt.figure(figsize=(10, 5))
plt.plot(t, x, 'b', label="Original Signal (Continuous)")
plt.stem(n, xn, 'r', markerfmt='ro', basefmt=" ", linefmt='r-', label="Sampled Signal")
plt.xlabel("Time (seconds)")
plt.ylabel("Amplitude")
plt.title("Ideal Sampling")
plt.legend()
plt.grid(True)
plt.show()
~~~
Output Waveform:
![WhatsApp Image 2025-03-22 at 15 37 18_3b4ba1ce](https://github.com/user-attachments/assets/7d3bac2d-87b0-4e7d-a058-a6029feac86e)



Results:
The original signal is sampled at fs=20Hz.
