# Verilog ALU Testbench

A vector-driven Verilog testbench for a 32-bit ALU with a 64-bit result and a zero flag. Only the testbench is included.

## Requirements

A Verilog simulator, a compatible `alu` module, `defines.v` defining the operation constants, and a nonempty `data.txt` vector file. The latter three dependencies are absent.

## Getting started

Obtain the matching definitions, ALU implementation, and vectors. The timescale directive is currently inside the module and must be moved or otherwise resolved for Icarus compatibility before compiling. Then select `alu_tb` as the simulation top and run from the vector-file directory.

## Project structure

| Path | Purpose |
| --- | --- |
| `alu_tb.v` | Operand generation and expected-result checks |

## Configuration and limitations

Each vector supplies six hexadecimal fields: operation, source operand 0, source operand 1, expected high result, expected low result, and expected zero flag. The bench checks arithmetic, comparisons, bitwise operations, shifts, multiplication/division, and subtraction’s zero flag.

## Development and validation

Both mismatch and completion use `$stop`. An empty/missing vector file can reach the `pass!` message without exercising the ALU. Require actual executed vectors and inspect failure messages; there is no self-contained passing test in this checkout.

## License

No root-level license file is included. Check source-specific notices and obtain permission before redistribution or reuse.
