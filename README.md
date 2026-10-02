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

## Testbench

The testbench applies all 8 possible combinations of the three inputs A, B, and Cin.

The simulation displays the resulting Sum and Cout values and generates a VCD waveform file for analysis using GTKWave.

## How to Run
1. Compile the Verilog Files
iverilog -o full_adder_sim full_adder.v tb_full_adder.v
2. Run the Simulation
vvp full_adder_sim
3. Open the Waveform
gtkwave full_adder.vcd
Expected Simulation Output
A B Cin | Sum Cout
0 0  0  |  0    0
0 0  1  |  1    0
0 1  0  |  1    0
0 1  1  |  0    1
1 0  0  |  1    0
1 0  1  |  0    1
1 1  0  |  0    1
1 1  1  |  1    1
Waveform

The generated full_adder.vcd file can be opened in GTKWave to inspect the input and output signal transitions.

The waveform contains the following signals:

A
B
Cin
Sum
Cout
Result

The 1-bit full adder was successfully implemented, compiled, simulated, and verified for all 8 possible input combinations.

Conclusion

This task provided practical experience with Verilog HDL, testbench development, digital circuit simulation, VCD waveform generation, and waveform analysis using GTKWave.
