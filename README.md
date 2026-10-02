# VLSI Task 1 - 1-Bit Full Adder

## Objective

The objective of this task is to understand the basic workflow of digital hardware design using Verilog HDL, simulation, and waveform analysis.

## Tools Used

- Icarus Verilog 13.0
- GTKWave 3.3.127
- MSYS2 UCRT64
- Verilog HDL

## Project Description

This project implements a 1-bit full adder using Verilog HDL.

A full adder has three inputs:

- A
- B
- Cin

and two outputs:

- Sum
- Cout

The logic equations used are:

- Sum = A XOR B XOR Cin
- Cout = (A AND B) OR ((A XOR B) AND Cin)

## Project Files

| File | Description |
|---|---|
| `full_adder.v` | Verilog design of the 1-bit full adder |
| `tb_full_adder.v` | Testbench for verifying the full adder |
| `full_adder.vcd` | VCD waveform generated during simulation |
| `full_adder_sim` | Compiled simulation executable |

## Full Adder Verilog Code

```verilog
module full_adder(
    input A, B, Cin,
    output Sum, Cout
);

assign Sum = A ^ B ^ Cin;
assign Cout = (A & B) | ((A ^ B) & Cin);

endmodule
