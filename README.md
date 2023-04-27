# ADC_Col

![Docker command](/Images/pico_contest.png)

Follows the proposal of and ADC SAR for the SSCS "PICO" Open-Source Chipathon developed by:
- Juan Sebastián Moya Baquero
- David Alejandro Reyes
- Juan Andrés Loopez Cubides
- Fredy Enrique Segura Quijano

Follows a description of the main specifications defined for the ADC-SAR

##### ADCs Specifications
| **Specification**  | **Symbol** | **Baseline requirement** | **Comment** | 
| ------------- | ------------- | ------------- | ------------- |
| Sampling rate  | fs  | ≥ 1.5MS/s | |
| Effective number of bits | ≥ 9 | Measured near Nyquist |
| Input Capacitance | Cin | ≤ 5pF | |

We know that ENOB is defined by:

ENOB = (SNDR - 1.76dB)/6.02

Then, SNDR --> 6.02 x ENOB + 1.76dB

The next table presents the relation between ENOB and SNDR based on the equation above.

##### ADCs Specifications
| **ENOB**  | **SNDR** |
| ------------- | ------------- |
|  8 | 49.92 |
|  **9** | **55.94** |
|  10 | 61.96 |
|  11 | 67.98 |
|  12 | 74 |

Based on the information presented above and the specification of the contest, we must have SNDR ≥ 55.94



