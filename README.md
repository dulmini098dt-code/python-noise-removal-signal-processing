# python-noise-removal-signal-processing
Python project on noise removal using digital signal processing techniques.Visibility


Python Noise Removal Using Digital Signal Processing

About the Project

This is a Python-based noise removal project developed as part of my third-year university module, Data Acquisition and Signal Processing.

The main purpose of this project is to understand how digital signal processing techniques can be used to reduce noise in a signal.

Objectives

- Understand the effect of noise on signals.
- Apply digital signal processing concepts using Python.
- Explore the effect of different cutoff frequencies.
- Compare the original noisy signal with the filtered signals.

Methodology

1. Generate or obtain a noisy signal.
2. Apply the noise-removal filtering process using Python.
3. Test different cutoff frequency values.
4. Plot and compare the signal results.
5. Observe how the cutoff frequency affects noise removal.

Tools and Technologies

- Python
- Digital Signal Processing concepts

Learning Outcomes

Through this project, I gained practical experience in Python programming and learned how filtering techniques can be applied to signal processing problems.

Project Documentation

- Project Report: [https://canva.link/e7iwfemgnzn11lg]



https://docs.google.com/document/d/1cH2II1zxL0G_yRcOamWVLsxgVzobP7g9c0cWdF4CoAY/edit?usp=drivesdk


https://canva.link/e7iwfemgnzn11lg

import numpy as np
import matplotlib.pyplot as plt

fs = 500
t = np.arange(0,2,1/fs)
print(t)

f = 5
original =np.sin(2* np.pi*f*t)

plt.plot(t,original)
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.title('original signal')
plt.grid(True)
plt.show()

np.random.seed(10)

noise =0.5*np.random.randn(len(t))
noise= original+noise

plt.plot(t,noise)
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.title('noisy signal')
plt.grid(True)
plt.show()

from scipy.signal import butter,filtfilt
cutoff=15
order=4
b,a =butter(order,cutoff, fs=fs,btype='low')
filtered = filtfilt(b,a,noise)

plt.plot(t,filtered)
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.title('filtered signal')
plt.grid(True)
plt.show()


