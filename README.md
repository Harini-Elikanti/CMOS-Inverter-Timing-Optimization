# CMOS Inverter Design & Timing Optimization

## Overview

Designed and characterized a CMOS inverter using LTspice and a TSMC 180-nm BSIM transistor model. The design was evaluated through DC transfer characteristics and transient analysis, followed by transistor sizing optimization to study its impact on switching performance.

## Objectives

- Design a CMOS inverter using NMOS and PMOS transistors.
- Analyze the DC Voltage Transfer Characteristic (VTC).
- Characterize transient switching behavior.
- Measure propagation delay, rise time, and fall time.
- Investigate the effect of PMOS sizing on inverter performance.

## Technology and Simulation Setup

| Parameter | Value |
|---|---:|
| Technology | 180 nm |
| Supply Voltage | 1.8 V |
| NMOS Length | 180 nm |
| NMOS Width | 900 nm |
| PMOS Length | 180 nm |
| PMOS Width | 900 nm / 1.8 µm |
| Load Capacitance | 1 pF |
| Temperature | 27 °C |
| Simulator | LTspice |
| Device Model | TSMC 180-nm BSIM |

## Circuit

The CMOS inverter consists of a PMOS pull-up transistor and an NMOS pull-down transistor connected at the output node.

## DC Analysis

A DC sweep of the input voltage from 0 V to 1.8 V was performed to obtain the Voltage Transfer Characteristic (VTC).

The inverter exhibits:

- VOH ≈ 1.8 V
- VOL ≈ 0 V
- Inverting voltage-transfer behavior
- High gain in the transition region

## Transient Analysis

A periodic input pulse was applied to characterize the switching response.

### Baseline Design

NMOS:
- W = 900 nm
- L = 180 nm

PMOS:
- W = 900 nm
- L = 180 nm

Measured timing:

| Parameter | Result |
|---|---:|
| tPHL | 1.710 ns |
| tPLH | 3.822 ns |
| Rise Time | 7.950 ns |
| Fall Time | 3.100 ns |
| Average Propagation Delay | 2.766 ns |

## PMOS Sizing Optimization

The PMOS width was increased from 900 nm to 1.8 µm while keeping the NMOS unchanged.

### Comparison

| Parameter | PMOS = 900 nm | PMOS = 1.8 µm |
|---|---:|---:|
| tPHL | 1.710 ns | 1.716 ns |
| tPLH | 3.822 ns | 2.011 ns |
| Rise Time | 7.950 ns | 4.153 ns |
| Fall Time | 3.100 ns | 3.102 ns |
| Average Delay | 2.766 ns | 1.864 ns |

### Observation

Increasing PMOS width significantly improves the pull-up drive strength.

The average propagation delay decreased from approximately:

2.766 ns → 1.864 ns

representing approximately a 32.6% reduction.

The low-to-high propagation delay also decreased substantially because the wider PMOS charges the capacitive load more quickly.

## Key Learnings

- CMOS inverter operation and voltage transfer characteristics
- MOSFET sizing and drive strength
- Propagation delay characterization
- Rise and fall time measurement
- Capacitive loading effects
- Pull-up/pull-down transistor strength
- SPICE-based circuit simulation and analysis
- Design trade-offs in CMOS digital circuits

## Tools Used

- LTspice
- SPICE
- TSMC 180-nm BSIM model

