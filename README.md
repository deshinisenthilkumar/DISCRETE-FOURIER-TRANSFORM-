# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
 To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close();
x = [1, 2, 3, 4];  
N = length(x);
disp("Input sequence x(n) = ");
disp(x);
X_direct = zeros(1, N); 
for k = 0:N-1
    sum_val = 0;
    for n = 0:N-1
        sum_val = sum_val + x(n+1) * exp(-%i * 2 * %pi * k * n / N);
    end
    X_direct(k+1) = sum_val;
end
disp("DFT using Direct Method:");
disp(X_direct);
X_fft = fft(x, -1); 
disp("DFT using FFT Function:");
disp(X_fft);
disp("Difference between Direct DFT and FFT:");
disp(X_direct - X_fft);
k = 0:N-1;

subplot(2,2,1);
plot2d3(k, abs(X_direct));
title("Magnitude Spectrum (Direct DFT)");

subplot(2,2,2);
plot2d3(k, angle(X_direct));
title("Phase Spectrum (Direct DFT)");

subplot(2,2,3);
plot2d3(k, abs(X_fft));
title("Magnitude Spectrum (FFT)");

subplot(2,2,4);
plot2d3(k, angle(X_fft));
title("Phase Spectrum (FFT)");
```
# OUTPUT: 
<img width="500" height="300" alt="Screenshot 2025-11-26 192228" src="https://github.com/user-attachments/assets/1bd56335-2b4f-4353-bd29-a4449a3ebd8d" />

# RESULT: 
The DFT of the given sequence was computed using direct and FFT methods, giving identical magnitude and phase spectra.
