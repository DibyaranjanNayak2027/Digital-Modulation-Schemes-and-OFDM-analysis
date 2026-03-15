# Digital-Modulation-Schemes-and-OFDM-analysis
This repository contains MATLAB simulations and performance analysis of digital modulation schemes (BPSK, QPSK, 16QAM, Binary ASK) and OFDM systems under various channel conditions. The focus is on evaluating Bit Error Rate (BER) vs. Signal-to-Noise Ratio (SNR) across AWGN, Rayleigh, and Rician fading channels.


Modulation Schemes:-
->ASK (Amplitude Shift Keying)  
  Information is encoded by varying the amplitude of the carrier wave. Simple but highly sensitive to noise and fading.

->PSK (Phase Shift Keying)  
  Information is carried by changing the phase of the carrier.

->BPSK (Binary PSK): Uses two phases (0° and 180°). Very robust, but only 1 bit per symbol.

->QPSK (Quadrature PSK): Uses four phases (0°, 90°, 180°, 270°). Carries 2 bits per symbol, doubling efficiency compared to BPSK.

->16-QAM (Quadrature Amplitude Modulation)  
  Combines amplitude and phase variations. 16 distinct constellation points → 4 bits per symbol. Higher data rate but more sensitive to noise and fading
 
OFDM (Orthogonal Frequency Division Multiplexing)
-Splits the channel into many narrowband subcarriers, each modulated separately (often with QAM or PSK).

-Subcarriers are orthogonal, preventing interference.

-Excellent for combating multipath fading and used in modern systems like Wi-Fi, LTE, and 5G

Channel Models
->AWGN (Additive White Gaussian Noise Channel):  
  Simplest model. Assumes only random Gaussian noise is added to the signal. No fading, just noise.

->Rayleigh Fading Channel:  
  Models multipath propagation where there is no line-of-sight (LOS) path. Signal amplitude follows a Rayleigh distribution. Common in dense urban environments.
  

->Rician Fading Channel:  
 Similar to Rayleigh, but includes a dominant LOS component along with multipath. Signal amplitude follows a Rician distribution. More stable than Rayleigh  because of the strong direct path.


 Individual Graph Analyses
1. BER vs. SNR for BPSK, QPSK, 16QAM under AWGN, Rayleigh, Rician
AWGN channel:
All modulation schemes show exponential BER reduction with increasing SNR.
BPSK and QPSK outperform 16QAM, especially at low SNR, due to lower symbol error probability.

Rayleigh fading:
BER performance degrades significantly compared to AWGN.
Diversity is absent, so fading dominates error probability.
16QAM suffers the most, highlighting its sensitivity to fading.

Rician fading:
Performance lies between AWGN and Rayleigh.
Presence of a line-of-sight component reduces fading severity.
BPSK/QPSK remain more robust than 16QAM.

2. OFDM BER under Rayleigh Fading
BER decreases with SNR, but the slope is shallow compared to AWGN.
Multipath fading causes deep fades across subcarriers, leading to error bursts.
OFDM mitigates ISI but remains vulnerable to Rayleigh fading without diversity or coding.
It moderate SNR (~10 dB), BER is still relatively high compared to AWGN performance.

3. OFDM BER under Rician Fading
BER performance improves compared to Rayleigh due to the line-of-sight path.
At higher SNR (>12 dB), BER approaches AWGN-like behavior.
OFDM benefits from frequency diversity, but fading still introduces error floors at low SNR.
The curve shows a steeper decline than Rayleigh, confirming robustness in Rician channels.

4. OFDM BER under AWGN
BER decreases sharply with SNR, showing ideal performance.
At ~10 dB SNR, BER is already below 
10^-3
This represents the baseline performance of OFDM without fading impairments.
Confirms OFDM’s efficiency in purely noisy channels.

5. BER vs. SNR for Binary ASK under AWGN, Rayleigh, Rician
AWGN channel:
Best performance, BER drops rapidly with SNR.

Rayleigh fading:
Worst performance, BER remains high even at 20 dB SNR.
ASK is highly sensitive to amplitude variations caused by fading.

Rician fading:
Intermediate performance, better than Rayleigh but worse than AWGN.
Line-of-sight reduces fading severity, but ASK still suffers compared to phase-based schemes (BPSK/QPSK).

Key Observations
AWGN channels always yield the best BER performance across all schemes.
Rician fading provides a middle ground, showing the importance of LOS paths.
Rayleigh fading is the harshest environment, exposing weaknesses in higher-order modulation and ASK.
OFDM is robust in AWGN but requires diversity/coding to handle fading effectively.
Phase-based modulations (BPSK/QPSK) outperform amplitude-based ASK in fading channels.
Higher-order schemes (16QAM) trade spectral efficiency for error resilience, performing poorly at low SNR.

Conclusion
For low-SNR and fading environments, BPSK/QPSK are most reliable.
For high data rates in AWGN, 16QAM is efficient but fragile in fading.
Binary ASK is unsuitable for fading channels due to amplitude sensitivity.
OFDM provides robustness against ISI but still requires channel coding/diversity to combat fading.

Results Discussion
The graphs show how different modulation schemes and OFDM systems behave when the signal passes through different types of channels. The main takeaway is that the quality of the channel has a huge impact on how many errors occur.

Channel Effects
In a simple noisy channel (AWGN), performance is the best. Errors drop quickly as the signal strength improves.
In Rayleigh fading, performance is the worst. Without a direct line-of-sight path, signals bounce around and interfere, causing many errors even at high signal strength.
Rician fading sits in between. Because there is at least one strong direct path, errors are fewer compared to Rayleigh, but still worse than AWGN.

Modulation Schemes
BPSK and QPSK are the most reliable. They keep error rates low even when the channel is bad, which makes them good choices for tough environments.
16QAM can carry more data, but it struggles in fading channels. At low signal strength, it produces many errors, showing the trade-off between speed and reliability.
Binary ASK is very sensitive to fading because it depends on amplitude, which gets distorted easily. It works fine in AWGN but performs poorly in Rayleigh and Rician channels.

OFDM Systems
In AWGN, OFDM works extremely well, quickly reducing errors as signal strength increases.
In Rayleigh fading, OFDM struggles. Errors don’t drop as fast, and there’s a kind of “error floor” where performance stops improving.
In Rician fading, OFDM does much better. With a line-of-sight path, performance comes close to the AWGN case at higher signal strengths.

Comparisons Across All Graphs
AWGN always gives the best results.
Rician fading is better than Rayleigh because of the line-of-sight path.
Phase-based schemes (BPSK, QPSK) are more robust than amplitude-based ASK.
Higher-order schemes like 16QAM are efficient but fragile.
OFDM is strong against interference but still needs coding or diversity techniques to handle fading properly.
