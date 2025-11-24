# Auto-Correlation-and-PSD

### Aim:

Write a program for Autocorrelation anmd PSD of signals in SCILAB and verify Wiener-Khinchin relation.

---

### Apparatus Required:

- Computer with i3 processor
- SCILAB

---

### Theory:

The Wiener-Khinchin theorem states that the power spectral density of a wide sense stationary random process is the Fourier transform of the corresponding autocorrelation function.

$$PSD = S_{xx}(\omega) = FT[R_{xx}(\tau)] = \int_{-\infty}^{\infty} R_{xx} (\tau) e^{-j \omega t} dt$$

$$ACF = R_{xx}(\tau) = l FT [S_{xx}(\omega)] = \frac{1}{2 \pi} \int_{-\infty}^{\infty} S_{xx} (\omega) e^{j \omega t} d \omega$$

---

### Algorithm:

1. Load or Define the Signal: Input uor time-domain signal.
2. Computa Autocorrelation: Calculate the autocorrelation function of the signal.
3. Compute Power Spectral Density (PSD): Estimate the PSD of the signal, either directly using a method like Welch's periodogram or by using the Fourier transform of the autocorrelation.
4. Plot Results: Visualize the autocorrelation function and PSD.

---

### Procedure:

- Refer Algorithms and write code for the experiment.
- Open SCILAB in System.
- Type your code in New Editor.
- Save the file.
- Execute the code.
- If any error, correct it in code and execute again.
- Verify the generated waveform using Tabulation and Model Waveform.

---

### Program:

```sci
Am=4.7
Ac=9.7
fm=360;
fc=3600;
fs = 36000;                   
t = 0:1/fs:1;                
x = sin(6*t);
[acor, lag] = xcorr(x, x);   
N = length(x);
X = fft(x);
PSD = (1/(fs*N)) * abs(X).^2;
f = (0:N-1)*(fs/N);
subplot(3,1,1);
plot(t, x);
subplot(3,1,2);
plot(lag/fs, acor);
subplot(3,1,3);
plot(f, PSD);

```

---

### Output:

<img width="1918" height="1198" alt="image" src="https://github.com/user-attachments/assets/244347d7-3364-4bd7-9ef0-406615dd47c4" />

---

### Result:

Thus the Autocorrelation and PSD are executed in Scilab and output is verified.
