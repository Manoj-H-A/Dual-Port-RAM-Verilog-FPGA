# Dual-Port-RAM-Verilog-FPGA

## Overview

This project implements a simple Dual-Port RAM (DPRAM) using Verilog HDL and targets the Artix-7 FPGA (Arty A7 Development Board).

Dual-Port RAM allows simultaneous access to memory through multiple ports, improving system performance in applications requiring parallel memory operations.

## Features

* Simultaneous memory access
* Independent read ports
* Synchronous write operation
* Verilog HDL implementation
* FPGA implementation on Arty A7 (Artix-7)
* Simulation and synthesis verified

## Design Specifications

| Parameter       | Value             |
| --------------- | ----------------- |
| Memory Size     | 4 Locations       |
| Data Width      | 1 Bit             |
| Address Width   | 2 Bits            |
| Write Operation | Synchronous       |
| Read Operation  | Synchronous       |
| FPGA Board      | Arty A7 (Artix-7) |
| HDL             | Verilog           |

## Block Diagram

The design consists of:

* Memory Array
* Write Enable Signal
* Write Address Port
* Two Independent Read Address Ports
* Two Read Outputs
* Common Clock Signal

## Working Principle

1. Initialize memory locations.
2. On every positive clock edge:

   * If Write Enable is high, write data into memory.
   * Read data simultaneously from two independent read addresses.
3. Display outputs through both read ports.

## Verilog Module

The Dual-Port RAM is implemented using a memory array and synchronous logic.

### Inputs

* clk
* we
* din
* waddr
* raddr_a
* raddr_b

### Outputs

* a
* b

## Simulation

The testbench performs:

* Clock generation
* Sequential write operations
* Parallel read operations
* Functional verification

Simulation confirms:

* Correct write operation
* Simultaneous read access
* Data integrity

## FPGA Implementation

Target Device:

* Xilinx Artix-7 FPGA
* Arty A7 Development Board

The design was synthesized and implemented successfully using Xilinx Vivado.

## Applications

* Multi-Processor Systems
* FIFO Buffers
* Embedded Systems
* Communication Systems
* Signal Processing Systems

## Advantages

* Faster Memory Access
* Reduced Latency
* Parallel Processing Support
* Efficient Hardware Utilization

## Results

The Dual-Port RAM was successfully designed, simulated, synthesized, and implemented on the Artix-7 FPGA platform. The design demonstrates parallel memory access using two independent read ports.

## Authors

Team 09

* Manoj H A
* E Sai Lakshmi
* Aditya P V
* Yogesh

## Tools Used

* Verilog 
* Xilinx Vivado
* Arty A7 FPGA Board

