# python-noise-removal-signal-processing
Python project on noise removal using digital signal processing techniques.Visibility


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


