# Single-Cycle MIPS
A System Verilog processor design of a single cycle MIPS architecture. 
Available for running at:
https://www.edaplayground.com/x/5Eje  
___
  
![alt text](https://github.com/naftali10/Single-Cycle_MIPS/blob/main/SIngle%20Cycle%20MIPS%20Diagram.png "Processor's diagram")
## Architecture data:  
R-type instrictions (add, sub, set less than, jump register) structure:
| Op |	rs |	rt |	rd |	shamt |	funct |
| - | - | - | - | - | - |
| 6 bits	| 5 bits | 5 bits |	5 bits | 5 bits |	6 bits |

I-type (load word, store word, branch not equal, branch equal, add immediate, load upper immediate) structure:
| Op	| rs	| rt	| Immediate value / address offset (in 2's complement) |
| - | - | - | - |
| 6 bits |	5 bits |	5 bits |	16 bits |

Common instructions and resulting signals of ALUOp and ALU control:
| Instruction	| Opcode  | Funct	| ALUOp	| ALU ctrl	| Function |
| --- | -- | -- | -- | --- | --- |
| lw  | 35 | -- | 00 | 010 | ADD |
| sw  | 43 | -- | 00 | 010 | ADD |
| beq | 4  | -- | 01 | 110 | SUB |
| add | 0  | 32 | 10 | 010 | ADD |
| sub | 0  | 34 | 10 | 110 | SUB |
| and | 0  | 36 | 10 | 000 | AND |
| or  | 0  | 37 | 10 | 001 | OR  |
| slt | 0  | 42 | 10 | 111 | SLT |
