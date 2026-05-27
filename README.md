# EXP 3 : IIR-CHEBYSHEV-FITER-DESIGN

## AIM: 

 To design an IIR Chebyshev filter  using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (LPF): 

```clear;

// Sampling frequency
Fs = 5000;          // Hz

// Cutoff frequency
fc = 1500;          // Hz

// Butterworth LPF order 3 coefficients (Chebyshev Type I, 1 dB ripple)
// Precomputed numerator (b) and denominator (a)
b = [0.0929 0.2787 0.2787 0.0929];   // Numerator coefficients
a = [1.0000 -0.5772 0.4218 -0.0561];  // Denominator coefficients

// Frequency response
Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);

// Convert normalized frequency to Hz
f = f_norm * Fs;

// Plot magnitude response in dB
clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I Low Pass Filter (Order 3)");
xgrid();

// Display coefficients
disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");
```

## PROGRAM (HPF): 
```clear;

// Sampling frequency
Fs = 5000;          // Hz

// Cutoff frequency
fc = 1500;          // Hz

// Chebyshev HPF order 3 coefficients (Type I, 1 dB ripple)
// Precomputed numerator (b) and denominator (a)
b = [0.4218 -0.5772 0.2787 -0.0929];   // Numerator coefficients
a = [1.0000 -0.5772 0.4218 -0.0561];   // Denominator coefficients

// Frequency response
Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);

// Convert normalized frequency to Hz
f = f_norm * Fs;

// Plot magnitude response in dB
clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I High Pass Filter (Order 3)");
xgrid();

// Display coefficients
disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");
```


## OUTPUT (LPF) : 
<img width="1912" height="1078" alt="image" src="https://github.com/user-attachments/assets/ba481c72-8ccd-4ac7-8015-80883f16bd3c" />


## OUTPUT (HPF) : 
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/d9adbbd5-538c-4bb1-b33a-e8974f4d6a92" />


## RESULT: 
A 3rd-order Chebyshev Type I high-pass filter was designed with cutoff frequency 1500 Hz and sampling frequency 5000 Hz. The frequency response shows ripple in the passband and sharp attenuation in the stopband.
