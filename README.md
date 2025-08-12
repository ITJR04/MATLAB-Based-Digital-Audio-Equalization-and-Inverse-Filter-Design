# MATLAB-Based-Digital-Audio-Equalization-and-Inverse-Filter-Design
Overview
This project focuses on analyzing and correcting distortions in audio systems through transfer function estimation and inverse filter design. Using MATLAB, we identify imperfections in a system’s frequency response—caused by factors such as speaker limitations or room acoustics—and apply corrective filtering to restore audio quality. The project also demonstrates bass boost and treble boost enhancements to selectively amplify specific frequency ranges.

Objectives
Estimate the magnitude of the system’s transfer function using provided input and output audio signals.

Design and implement an inverse filter to flatten the frequency response and remove distortions.

Evaluate the effectiveness of the filter through time-domain and frequency-domain analysis.

Demonstrate audio enhancement techniques such as bass and treble boosting.

# Methodology
1. Transfer Function Estimation
The magnitude of the transfer function, 
∣𝐻(𝜔)∣
∣H(ω)∣, is calculated using:

∣𝐻(𝜔)∣ = sqrt(𝑃𝑦𝑦(𝜔)/𝑃𝑥𝑥(𝜔))

where 
𝑃𝑦𝑦 and 𝑃𝑥𝑥 are the power spectra of the output and input signals, respectively.

MATLAB’s pwelch() function is used for spectral estimation, with results plotted on a logarithmic frequency scale.

2. Inverse Filter Design
The inverse filter is derived by taking the reciprocal of the estimated transfer function:

𝐻inv(𝑠) = 1/(𝐻(𝑠))
 
Zeros and poles are identified based on the slope of the magnitude response (+20 dB/decade for zeros, −20 dB/decade for poles) to form an accurate transfer function model.

3. Signal Correction
MATLAB’s lsim() function simulates the system’s response to the distorted signal using the inverse filter.

The corrected signal is exported as a .wav file via audiowrite() for listening tests and further analysis.

4. Frequency Enhancement
Bass and treble boosting are simulated by modifying the transfer function to emphasize low or high frequencies, respectively.

Both waveform and spectral changes are analyzed to confirm targeted frequency amplification.

# Results
Correction: The inverse filter effectively removed distortions, producing an output signal closely matching the original input in both sound quality and spectral characteristics.

Enhancements: Bass boost increased lower-frequency components (e.g., guitar), while treble boost emphasized higher-frequency elements (e.g., bells, snare, vocals).

Validation: Power spectrum plots confirmed the correlation between original and corrected signals, and listening tests verified perceptual improvements.
plots:
<img width="313" height="239" alt="Bass boost tf" src="https://github.com/user-attachments/assets/45933bc0-a848-4125-9782-d2a89f3a8db7" />
<img width="278" height="227" alt="bode of estimated inv tf" src="https://github.com/user-attachments/assets/587fb3d4-163c-475f-a9a6-21611bce2003" />
<img width="295" height="230" alt="Bode of estimated tf" src="https://github.com/user-attachments/assets/a169ad0a-7da8-4b38-a24f-9b43edb81ea1" />
<img width="281" height="233" alt="Estimated tf magnitude" src="https://github.com/user-attachments/assets/299009e5-1286-43c3-8396-d579629a5cf9" />
<img width="300" height="235" alt="power spectrum of bass boosted sounds" src="https://github.com/user-attachments/assets/b666371b-9e28-4f00-9854-87bf2f51a9b0" />
<img width="286" height="223" alt="Power spectrum of original, distorted and corrected sound" src="https://github.com/user-attachments/assets/24dbe650-714d-4f5c-b929-ace3e4f1c811" />
<img width="284" height="224" alt="Power spectrum of treble boosted sounds" src="https://github.com/user-attachments/assets/b0174ecc-5364-451f-bdc1-44f89990151a" />
<img width="287" height="226" alt="Time waveforms of original, distorted and corrected sounds" src="https://github.com/user-attachments/assets/37217a5a-4ca2-4af4-b94b-490037333665" />
<img width="283" height="225" alt="Time waveforms of treble boosted sounds" src="https://github.com/user-attachments/assets/00c2f33f-830f-4594-bb1d-e68630d7353b" />
<img width="287" height="236" alt="Treble boost tf" src="https://github.com/user-attachments/assets/354ff84c-c120-4673-9412-580ef7ce8813" />



# Key MATLAB Functions Used
pwelch() – Power spectral density estimation

semilogx() – Logarithmic frequency response plotting

tf() – Transfer function creation

lsim() – Linear system simulation

audiowrite() – Audio file export

plot() – Time-domain visualization

# Conclusion
This project demonstrates how digital signal processing techniques can accurately restore and enhance audio signals by:

Analyzing a system’s frequency response

Designing an inverse filter to remove distortions

Applying targeted frequency boosts for creative enhancement

The combination of transfer function analysis, inverse filtering, and frequency-specific processing highlights the importance of MATLAB in developing robust audio equalization solutions.
