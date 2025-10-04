# fundamentals of babySoC

## Introduction

A System-on-Chip (SoC) integrates the main components of a computing system - processor cores, memory, I/O and peripherals - all onto a single silicon die.which consolidation improves power, performance, and area efficiency, and is widely used in mobile and embedded devices.

## What is an SoC?

A SoC is an integrated circuit that brings together processor cores, memory blocks, communication fabrics, and peripheral interfaces to implement a complete system. By integrating multiple blocks on a single die, SoCs reduce board complexity and power consumption while enabling higher performance for compact devices.

## Typical components of an SoC

* **Processor core(s)**: one or more CPU cores (general-purpose CPU, microcontroller, DSP, or accelerator).
* **Memory**: on-chip RAM, ROM/flash interfaces, cache controllers.
* **Peripherals**: timers, UART, SPI, I²C, GPIO, ADC/DAC, and other interface controllers.
* **Interconnect**: bus or network-on-chip (NoC) that connects blocks (AMBA/AXI, AHB, APB are common).
* **Power & Clock management**: regulators, PLLs, clock gating for power domains.

## Why BabySoC (a simplified learning model)?

BabySoC is a reduced-complexity SoC model used for learning core SoC concepts without the overhead of full-scale commercial designs. It strips the system down to a minimal CPU, memory, and a couple of peripherals plus a simple bus/interconnect, allowing students to focus on architecture, data flow, and verification using simulation tools.

## Role of functional modelling

Functional modelling (behavioral or high-level functional description) is performed before RTL and physical design to validate the architecture and expected behavior of the SoC. This stage helps catch architectural bugs, validate instruction sequences and peripheral interactions, and define interfaces and expected waveforms prior to committing to RTL.

## Tools used (simulation & waveform viewing)

* **Icarus Verilog**: open-source Verilog simulator used to compile and run testbenches and generate waveform dumps (VCD/LXT).
* **GTKWave**: waveform viewer to inspect simulation dumps and verify signal interactions and timing.

