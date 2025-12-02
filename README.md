Project Description

This project implements an 8-bit adder using the Xilinx Vivado Adder/Subtractor IP.
The goal is to integrate a pre-built IP block into a top-level Verilog module and verify correct functionality through simulation. The adder accepts two 8-bit unsigned inputs (A_0 and B_0) and produces a 9-bit output (S_0) that includes the carry-out bit.

The design consists of:

A Vivado-generated IP block (design_adder)

A top-level wrapper (Adder_top.v) that instantiates the IP

A testbench (Adder_top_tb.v) used to simulate and validate the adder

This project is part of Lab 11 for ECE 128 and demonstrates the workflow of configuring, instantiating, and testing Vivado IP cores.

Source Files

Adder_top.v
Top-level wrapper module that connects the IP core to external ports.

Adder_top_tb.v
Testbench used to simulate input vectors, generate waveform output, and print live results.

Instructions for Simulation
1. Open the Vivado Project

Create or open your Vivado RTL project that contains:

The block design that generated design_adder

The wrapper module Adder_top.v

2. Add the Testbench

In the “Simulation Sources” folder:

Add Adder_top_tb.v as a simulation-only file.

3. Run Behavioral Simulation

Open Flow Navigator → Simulation → Run Behavioral Simulation

Vivado will:

Compile both modules

Run the testbench

Produce console output via $monitor

Generate the waveform file specified in $dumpfile

4. View Waveforms

Open the Waveform window to inspect:

Inputs A and B

Output S

Timing behavior across the simulation

Instructions for FPGA Implementation
1. Ensure a Synthesizable Top Module

Confirm Adder_top.v is set as the project’s top module.

2. Run Synthesis

Use Flow Navigator → Run Synthesis.
After synthesis completes, open the utilization report to review:

LUT usage

Register count

Carry-chain resources used by the IP adder

3. Run Implementation

After synthesis, select Run Implementation to place and route the design on the FPGA.

4. Generate Bitstream

Choose Generate Bitstream to produce the programming file.

5. Program the FPGA

Connect the Basys3 board and program it using:

Hardware Manager → Open Target → Program Device

For hardware testing, drive A_0 and B_0 using switches or external logic and observe the output S_0 on LEDs or other connected hardware pins (as applicable to the lab requirements).
