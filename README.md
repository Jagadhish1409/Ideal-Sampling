AIM:

To demonstrate ideal sampling of a continuous signal using Scilab, ensuring accurate signal reconstruction while avoiding aliasing

COMPONENTS REQUIRED:

Scilab software.

PROGRAM:
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

  OUTPUT WAVEFORMS:

![Image](https://github.com/user-attachments/assets/560f416a-7a40-4696-83c6-72e544b007a9)
![Image](https://github.com/user-attachments/assets/9e04bca2-eab2-4542-8fc5-bb9179a85d9e)
![Image](https://github.com/user-attachments/assets/1fd4bdbd-6dbd-4134-b0a8-e46fab91a86d)

RESULT:

Ideal sampling captures a continuous signal at perfect intervals, ensuring accurate reconstruction if sampled at twice the highest frequency (Nyquist rate). It’s a key concept in digital signal processing and telecommunications. Practical systems approximate ideal sampling with some limitations.
