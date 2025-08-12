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


<img width="281" height="233" alt="Estimated tf magnitude" src="https://github.com/user-attachments/assets/ebba3841-3fad-4019-be9b-7f70053b583a" />
<img width="295" height="230" alt="Bode of estimated tf" src="https://github.com/user-attachments/assets/e4b9d186-270f-49bf-a7d6-cfef5df0853d" />
<img width="278" height="227" alt="bode of estimated inv tf" src="https://github.com/user-attachments/assets/0ce56503-60a9-4b49-9301-bb61be5e2327" />
<img width="287" height="226" alt="Time waveforms of original, distorted and corrected sounds" src="https://github.com/user-attachments/assets/16d1279e-1b85-4eaa-9926-9547a593818e" />
<img width="286" height="223" alt="Power spectrum of original, distorted and corrected sound" src="https://github.com/user-attachments/assets/ce7106de-a618-431d-844e-15b643e3640b" />
<img width="313" height="239" alt="Bass boost tf" src="https://github.com/user-attachments/assets/250e70cc-4c6a-47b8-9fdb-e5a1e2d377df" />
<img width="287" height="236" alt="Treble boost tf" src="https://github.com/user-attachments/assets/a2c0d27f-80f0-4342-b2c7-bb933a4895d5" />
<img width="362" height="287" alt="Time waveforsm of bass boosted sounds" src="https://github.com/user-attachments/assets/edc6617c-4c17-4ba2-91c5-b91531788938" />
<img width="283" height="225" alt="Time waveforms of treble boosted sounds" src="https://github.com/user-attachments/assets/808ef714-2966-4bfb-84cc-2cec858440eb" />
<img width="300" height="235" alt="power spectrum of bass boosted sounds" src="https://github.com/user-attachments/assets/c838c900-b248-41cf-be12-5e0cc545dbce" />
<img width="284" height="224" alt="Power spectrum of treble boosted sounds" src="https://github.com/user-attachments/assets/1a0c79ff-fc64-404a-8a87-488765411793" />


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
