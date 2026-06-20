# Dual-Port RAM Implementation on Arty A7 FPGA using Verilog HDL

## Project Overview

This project demonstrates the design, simulation, synthesis, and FPGA implementation of a **Dual-Port RAM** using **Verilog HDL** on the **Digilent Arty A7-100T FPGA Development Board**.

Dual-Port RAM is a specialized memory architecture that allows simultaneous access to memory through multiple ports. Unlike conventional single-port memory, DPRAM enables parallel read operations, reducing memory bottlenecks and improving overall system performance in digital systems.

The design was developed, verified through simulation, synthesized using Xilinx Vivado, and implemented on an Artix-7 FPGA.

The objective of this project is to design a memory system that supports:

* One write port
* Two independent read ports
* Simultaneous memory access
* Synchronous operation with clock control

---

## Hardware and Software Used

### Hardware

* Digilent Arty A7-100T FPGA Development Board
* Xilinx Artix-7 XC7A100T FPGA

### Software

* Xilinx Vivado Design Suite
* Verilog HDL

## Design Specifications

| Parameter       | Specification      |
| --------------- | ------------------ |
| Memory Type     | Dual-Port RAM      |
| Memory Depth    | 4 Locations        |
| Data Width      | 1 Bit              |
| Address Width   | 2 Bits             |
| Write Operation | Synchronous        |
| Read Operation  | Synchronous        |
| HDL             | Verilog            |
| FPGA Board      | Arty A7-100T       |
| FPGA Device     | XC7A100T (Artix-7) |

---

## Key Features

* Simultaneous access through two independent read ports
* Synchronous write operation
* Parallel memory access
* Low-latency memory communication
* FPGA implementation and verification
* Suitable for embedded and digital system applications

---

### Operation

1. Data is written into memory when the write enable signal is active.
2. Read Port A accesses memory location specified by `raddr_a`.
3. Read Port B accesses memory location specified by `raddr_b`.
4. Both read ports can operate simultaneously without interference when accessing different addresses.

---

## Algorithm

1. Initialize memory locations to zero.
2. Wait for the positive edge of the clock.
3. Check the write enable signal.
4. If write enable is HIGH:

   * Write input data into the selected memory location.
5. Read data from address `raddr_a`.
6. Read data from address `raddr_b`.
7. Update output ports.
8. Repeat for every clock cycle.

---

## Verilog Design Description

The RAM is implemented using a register array representing four memory locations.

### Inputs

| Signal  | Description         |
| ------- | ------------------- |
| clk     | System Clock        |
| we      | Write Enable        |
| din     | Data Input          |
| waddr   | Write Address       |
| raddr_a | Read Address Port A |
| raddr_b | Read Address Port B |

### Outputs

| Signal | Description        |
| ------ | ------------------ |
| a      | Data Output Port A |
| b      | Data Output Port B |

The design performs write operations and dual read operations synchronously on the rising edge of the clock.

---

## Testbench Verification

A dedicated testbench was developed to verify the functionality of the design.

### Testbench Operations

* Generates a clock signal
* Writes data into memory locations
* Disables write mode
* Reads data simultaneously through both ports
* Verifies memory contents

### Verification Results

* Successful write operations
* Correct data retrieval
* Simultaneous dual-port read functionality
* No memory conflicts during access

---

## Simulation Results

Simulation was performed using Xilinx Vivado Simulator.

Observed Results:

* Data was correctly written into memory.
* Read Port A successfully accessed selected memory locations.
* Read Port B simultaneously accessed different memory locations.
* Outputs matched expected values.

The simulation confirms correct Dual-Port RAM functionality.

---

## FPGA Implementation

The design was synthesized and implemented on the **Digilent Arty A7-100T FPGA Board**.

### Implementation Flow

1. RTL Design Entry
2. Behavioral Simulation
3. Synthesis
4. Implementation
5. Bitstream Generation
6. FPGA Programming

The generated bitstream was successfully downloaded onto the FPGA board and verified.

---

## Applications

Dual-Port RAM is widely used in:

* Multi-Processor Systems
* FIFO Buffers
* Embedded Systems
* Communication Systems
* Signal Processing Applications
* High-Speed Data Transfer Systems
* FPGA-Based Designs

---

## Advantages

* Faster memory access
* Parallel processing capability
* Reduced memory bottlenecks
* Efficient hardware utilization
* Lower system latency
* Improved overall performance

## Future Improvements

* Increase memory depth and data width
* Implement true dual-port read/write capability
* Add memory initialization from external files
* Develop parameterized RAM architecture
* Integrate with FPGA-based processors



## Conclusion

This project successfully demonstrates the design and implementation of a Dual-Port RAM using Verilog HDL on the Digilent Arty A7 FPGA platform.

The design supports simultaneous memory access through two independent read ports, enabling efficient parallel data operations. Simulation and synthesis results validate the correctness of the implementation, making it suitable for high-performance digital and embedded system applications.
