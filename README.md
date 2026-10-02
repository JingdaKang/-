# ALU Testbench

A Verilog testbench for a 32-bit arithmetic logic unit with a 64-bit result and a zero flag. The repository currently contains only `alu_tb.v`.

## What it checks

The testbench compares expected results for arithmetic, comparisons, bitwise operations, shifts, multiplication, and division. Subtraction also checks the zero flag.

## Requirements

- A Verilog simulator such as Icarus Verilog or ModelSim.
- `defines.v` defining the `ALUOP_*` constants.
- An `alu` module implementing the ports instantiated in `alu_tb.v`.
- A `data.txt` vector file in the simulator's working directory.

**The definitions, implementation, and vector file are not included in this repository.** Obtain matching files before trying to run the testbench.

## Vector format

Each record has six hexadecimal fields: operation, source operand 0, source operand 1, expected high result, expected low result, and expected zero flag. See the `$fscanf` call in `alu_tb.v` for the exact format.

## Running the testbench

After supplying the missing files, compile `alu_tb.v` together with the matching ALU implementation, select `alu_tb` as the top-level module, and launch the simulator from the directory containing `data.txt`.

The testbench uses `$stop` for both a mismatch and completion. Inspect its messages and confirm that vectors actually executed: an unreadable or empty vector file can reach the `pass!` message without testing the ALU.

## Repository contents

| File | Purpose |
| --- | --- |
| `alu_tb.v` | Clock generation, vector loading, and expected-result checks |

## License

No license file is included. Contact the repository owner before redistributing or incorporating the code into another project.
