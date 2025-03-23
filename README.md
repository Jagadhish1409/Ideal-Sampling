# EXP-1  IDEAL SAMPLING
# Name:JAGADHISH BABU R
# Reg no:212223060094

## AIM

To demonstrate ideal sampling of a continuous signal using Scilab, ensuring accurate signal reconstruction while avoiding aliasing

## COMPONENTS REQUIRED:

python IDE with Numpy and Scipy

## PROGRAM:
```python
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
```

 ## OUTPUT WAVEFORMS:
 
 ![image](https://github.com/user-attachments/assets/b2d89a89-7651-4a21-a180-e9cda8cfc395)
 
 ![image](https://github.com/user-attachments/assets/203e0379-fd3d-4162-ae7d-c107be1a0eab)
 
 ![image](https://github.com/user-attachments/assets/bd1dc349-e618-4e5c-a629-7838dcf3c25c)


## RESULT:

Ideal sampling captures a continuous signal at perfect intervals, ensuring accurate reconstruction if sampled at twice the highest frequency (Nyquist rate). It’s a key concept in digital signal processing and telecommunications. Practical systems approximate ideal sampling with some limitations.
