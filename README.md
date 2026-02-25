# Multi-Stage CMOS Analog Amplifier Design

## Overview
This repository contains the design, mathematical analysis, and LTspice simulation of a multi-stage CMOS analog amplifier. The project was designed from scratch to meet a strict set of target specifications, constraints, and physical limitations. 

## Architecture
The amplifier architecture consists of two main stages:
* **Input Stage:** A Single-Ended Common Source (CS) amplifier that provides initial gain and sets the input characteristics.
* **Output Stage:** A fully symmetrical Differential pair biased by a Current Mirror, providing additional gain and a differential output.
* **Coupling & Filtering:** Carefully sized capacitors are used for DC blocking and to precisely control the frequency response (poles and zeros) to meet the required roll-off slopes.

## Target Specifications vs. Simulated Results
The design successfully met all requested specifications with an error margin of less than 5%:

| Parameter | Target Specification | Simulated Result | Error |
| :--- | :--- | :--- | :--- |
| **Mid-Band Gain ($A$)** | 38 dB | 38.001 dB | < 0.01% |
| **Lower Cut-off ($f_L$)** | 7 kHz | 7 kHz | 0% |
| **Upper Cut-off ($f_H$)** | 700 kHz | 700 kHz | 0% |
| **Low-freq Slope ($M_1$)** | 40 dB/dec | 38.076 dB/dec | 4.8% |
| **High-freq Slope ($M_2$)** | -20 dB/dec | -19.962 dB/dec | 0.19% |
| **Output Resistance** | 11 kΩ | 11 kΩ | 0% |

*(Add your summary table image here)*

## Performance Plots

### Frequency Response (Bode Plot)
*(Add your Bode plot image here)*
The AC analysis demonstrates the precise mid-band gain of 38 dB and confirms the required bandwidth.

### Output Resistance
*(Add your output resistance graph here)*
The output resistance remains stable at 11 kΩ across the mid-band frequencies, as required by the design constraints.

## Physical Constraints
The design successfully operates under 5V $V_{DD}$ and adheres to strict limitations:
* **Total Resistance:** < 5 MΩ (Used: 0.53 MΩ)
* **Total Capacitance:** < 1 mF (Used: 0.0037 mF)
* **Power Consumption:** < 0.1 W (Used: ~9.06 mW)

## Getting Started
1. Install [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
2. Clone this repository.
3. Open `cmos_amplifier_design.asc` in LTspice to view the schematic and run the `.op` and `.ac` simulations.
