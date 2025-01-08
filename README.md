4-bit Sequential Multiplier in Verilog

This repository contains the Verilog implementation of a 4-bit Sequential Multiplier along with its testbench. The design performs sequential multiplication using shift-and-add logic, suitable for low-resource hardware designs.

Features

Sequential Multiplication: Implements a bit-by-bit shift-and-add algorithm for multiplying two 4-bit numbers.
Resource Efficiency: Ideal for hardware with limited resources, as the computation is performed sequentially over clock cycles.
Reset Functionality: Clears the internal registers and outputs, allowing for reinitialization.

Design Description

Module: seq_mulll_rtl
The sequential multiplier calculates the product of two 4-bit inputs (A and B) over multiple clock cycles.

Ports

Inputs:

clk: Clock signal.
reset: Synchronous reset signal.
A: 4-bit multiplicand.
B: 4-bit multiplier.

Output:

product: 8-bit result of the multiplication.

Functionality

On reset:
The inputs (A and B) are loaded into internal registers.
Internal counters and partial products are initialized to zero.
During multiplication:
The least significant bit (LSB) of the multiplier determines whether to add the shifted multiplicand to the partial product.
The multiplier is shifted right, and the process repeats for 4 clock cycles.
Final Result:
After 4 cycles, the product output holds the result of the multiplication.

Testbench Description

Module: seq_mulll_tb
The testbench verifies the functionality of the sequential multiplier by:

Applying various test cases with predefined values of A and B.
Monitoring the product output to ensure correctness.

Key Test Scenarios

Resetting the multiplier and verifying the cleared state.
Multiplying different sets of inputs (A and B) and validating the results.
