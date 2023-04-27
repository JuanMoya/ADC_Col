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

We base our project on the following Master Degree Dissertation [1]:

We develop the design of the ADC based on the following considerations regarding the tracking process of the SAR:
1) Finite resistance of the switch
2) Nyquist frequency
3) Switch stabilization time
4) Thermal Noise
5) Charge injection --> Charge is stored in the channel when the switch is in strong inversion.
6) Clock Feedthrough
7) Feedthrough  

We develop the design of the ADC based on the following considerations regarding the quantization process of the SAR:
1) Dynamic comparator since power consumption only occurs during the rising and falling edges.
2) Kickback noise in the dynamic comparator.
3) Static offset in the dynamic comparator.
4) Thermal noise.
5) Trade-off between thermal noise and power.
6) Metastability for small differential input voltages.
7) Conversion speed of the asynchronous operation is higher than the synchronous one.

The proposed ADC-SAR design is presented in the following figure.
![Docker command](/Images/propuesta.png)

The ADC-SAR proposed is composed of the following sub-circuits:

1) Differential Capacitive DAC
2) Switches for sampling
3) Bridge Capacitor
4) Dynamic Comparator
5) SAR Logic
6) Asynchronous operation to avoid the use of a high frequency clock.

### Sampling Switches 

We use the capacitor merged circuit for the sampling switches [2] --> The 11-bit ADC uses a 10-bit DAC.
Follows a 3-bit schematic using the merged capacitors.

![Docker command](/Images/merged_cap.png)

Since the common mode voltage of the outputs of the differential capacitive DAC is constant, the comparator offset is constant.

To solve the problem regarding injection charge and finite resistance, we use the bootstrap technique proposed in[2,3].

![Docker command](/Images/bootstrap.png)

## References

[1] **Reyes Gonzalez, D. A. Projeto de um conversor analógico-digital para um receptor UWB aplicado na detecção de câncer de mama em tecnologia CMOS (Master Thesis, Universidade de São Paulo).**
[2] **Hariprasath, V., Guerber, J., Lee, S. H., & Moon, U. K. (2010). Merged capacitor switching based SAR ADC with highest switching energy-efficiency. Electronics letters, 46(9), 620.**
[3]**Liu, C. C., Chang, S. J., Huang, G. Y., & Lin, Y. Z. (2010). A 10-bit 50-MS/s SAR ADC with a monotonic capacitor switching procedure. IEEE Journal of Solid-State Circuits, 45(4), 731-740.**
[4]
