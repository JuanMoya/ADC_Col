# ADC_Col

![Docker command](/Images/pico_contest.png)

Follows the proposal of and  11-bits SAR ADC for the SSCS "PICO" Open-Source Chipathon developed by:
- Juan Sebastián Moya Baquero
- David Alejandro Reyes Gonzalez
- Juan Andrés Lopez Cubides
- Fredy Enrique Segura Quijano

Follows a description of the main specifications defined for the SAR-ADC

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

We base our project on the following Master Degree Dissertation:

**Reyes Gonzalez, D. A. Projeto de um conversor analógico-digital para um receptor UWB aplicado na detecção de câncer de mama em tecnologia CMOS (Master Thesis, Universidade de São Paulo).**

The proposed ADC-SAR design is presented in the following figure.
![Docker command](/Images/propuesta.png)
