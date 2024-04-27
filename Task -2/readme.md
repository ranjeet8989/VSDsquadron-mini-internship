# RISCV 32I Instruction Set Architecture :-

1.Introduction 
  RISCV 32I ISA is the base integer instruction set architecture for RISCV Processors.it is very similar to early RISC Processor except  with no branch delay.Here's a brief overview of the key features and characteristics:

  - 32-bit Addressing:- The RISCV32 ISA operates on 32 bit addresses which allows it to access upto 4GB of memory directly.
  
  - Base Interger instruction:-Base refers to fundamental or essential subset of instruction that from the core of ISA.it includes
                              minimal set of instruction that are sufficient to provide basic functionality for software     
                              development,toolchain support like integer arithmetic and logical instructions, such as addition,   
                              subtraction, bitwise AND/OR/XOR, shifting, and comparison instructions.

  - Load and Store Instructions :- it provides instruction for loading data from memory (lw -load word ) and storing data to memory.
  
  - Immediate Instructions :- It supports immediate instructions where an immediate value is directly encoded in instruction for       
                             arithmetic and logical operations.

  - Branch Instruction:-Branch instruction allow for conditonal and uncondtional branching based on result of a comparison operation.
  
  - Jump and Link Instructions (JAL):-The ISA includes instructions for unconditonal jumps and jumps with links .
  
  - Control and Status Register (CSR) Instructions:-RISCV -ISA defines control and status registers that are used for privileged     
                                                   operations.

    # Types of levels of access and control of system resources :-

         
  | Unpriviliged State | Privileged State |
|----------|----------|
| Processor operates with restricted access to certain instructions and system resources | Processor has a full access to all instruction and system resource |
| User level programmed run in this state | Operating system kernals & system level software run in this state |
| prevents user programs from interfering with critical system functions | it allows oerating system to enforce security ploicies, manage,memory and coordinate teh execution multiple process or threads |

**Unprivileged State for Base Integer ISA RISCV 32I :-**

here , in this state we have total 32 registers.of each 32 bits wide .Register x0 is hardwired with all bits equal to 0.general purpose registers x1 -x31 hold value as signed or unsigned integer values.
PC (programme counter) is another additional register whcih hold the address of current instruction.

| registers |
| ------|
| x0 /0 |
| x1  |
| x2  |
| x3  |
| x4  |
| x5  |
| x6  |
| x7  |
| x8  |
| x9  |
| x10 |
| x11 |
| x12 |
| x13 |
| x14 |
| x15 |
| x16 |
| x17 |
| x18 |
| x19 |
| x20 |
| x21 |
| x22 |
| x23 |
| x24 |
| x25 |
| x26 |
| x27 |
| x28 |
| x29 |
| x30 |
| x31 |

|additional register|
|-----|
| PC |

*Fig 1: RISC-V base unprivileged integer register state.*


# RISCV-32I Instruction Format

1. R Type
   
   The R-Type instruction format in RISC-V 32I is used for arithmetic, logical, and shift instructions. It consists of the following     
   fields:
   
| 31       | 25 24   | 20 19   | 15 14   | 12 11   | 7 6     | 0       |
|----------|---------|---------|---------|---------|---------|---------|
| funct7   | rs2     | rs1     | funct3  | rd      | opcode  |   R     |



   - funct7(7 bits) :- it specifies the operatio code of instruction.
   - rs2 (5 bit) :- this field indicates the second source register used by the instruction.
   - rs1 (5 bit) :- source register 1 that indicates the first source register used by the instruction.
   - funct3 (3 bit) :- it specifies teh specific operation within the opcode category.
   - rd (5 bit) :- This field indicates the destination register where the result of the operation is stored.
   - opcode(7 bits) :- it specifies the operatio code of instruction.

  2. I Type
     
     The I type format is used for immediate arithmetic/logical instruction and loads.


    | 31     19|       15|         | 12     6|        0|
    |----------|---------|---------|---------|---------|
    | imm[11:0]| rs1     | funct3  | rd      | opcode  |

  - imm (12 bit) :-This field contains a 12-bit immediate value, sign-extended to   32 bits, which is used as an operand in the   
    instruction.
  - rs1: Source register 1. This field indicates the source register used by the instruction.
  - funct3: Function code 3. This field specifies the specific operation within the opcode category.
  - rd:  This field indicates the destination register where the result of the operation is stored.
  - opcode: This field specifies the operation code for the instruction.


3. S Type

The "S" instruction set in RISC-V 32I refers to the Store instructions. These instructions are used to store data from a register into memory

| 31-25   | 24-20   | 19-15   | 14-12   | 11-7    | 6-0      |
|---------|---------|---------|---------|---------|----------|
|imm[11:5]| rs2     | rs1     | funct3  | imm[4:0] | opcode  |

- imm[11:5]: Offset or immediate value, ranging from bit 11 to bit 5.
- rs2: Source register 2, holding the data to be stored.
- rs1: Source register 1, holding the base address in memory.
- funct3: Function code 3, specifying the operation (e.g., store byte, store halfword, store word).
- imm[4:0]: Additional immediate value or offset, ranging from bit 4 to bit 0.
- opcode: Operation code for the store instruction.
  
These instructions are fundamental for storing data in memory and are commonly used in assembly language programming for tasks such as manipulating arrays, accessing global variables, or interacting with memory-mapped peripherals.

 4. B Type
    
The "B" Type instruction in RISC-V architecture is used for conditional branch instructions. it allow the program to make decisions based on certain conditions, such as comparing values in registers.

| 31       | 30-25     | 24-20 | 19-15 | 14-12 | 11-8     | 7       | 6-0    |
|----------|-----------|-------|-------|-------|----------|---------|--------|
| imm[12]  | imm[10:5] | rs2   | rs1   | funct3| imm[4:1] | imm[11] | opcode |

- imm[12]: Immediate value, single bit, representing the most significant bit of the immediate.
- imm[10:5]: Immediate value, six bits, representing bits 10 through 5 of the immediate.
- rs2: Source register 2, five bits, specifying the second source register.
- rs1: Source register 1, five bits, specifying the first source register.
- funct3: Function code 3, three bits, specifying the operation.
- imm[4:1]: Immediate value, four bits, representing bits 4 through 1 of the immediate.
- imm[11]: Immediate value, single bit, representing the least significant bit of the immediate.
- opcode: Operation code, seven bits, specifying the type of instruction (e.g., branch).
   
5.U Type 

The "U" Type instruction in RISC-V architecture is used for unconditional jump instructions. These instructions allow the program to jump to a specific memory address unconditionally, typically used for implementing function calls or setting up the program's initial state.

| 31-12      | 11-7 | 6-0  |
|------------|------|------|
| imm[31:12] | rd   |opcode|

- imm[31:12]: Immediate value, 20 bits, representing bits 31 through 12 of the immediate.
- rd: Destination register, five bits, specifying the destination register where the result of the operation is stored.
- opcode: Operation code, seven bits, specifying the type of instruction (e.g., unconditional jump).

  **Here's a brief summary of the "U" Type instruction set:**
- LUI (Load Upper Immediate): Load a 20-bit immediate value into the upper 20 bits of a register, zeroing the lower 12 bits.
- AUIPC (Add Upper Immediate to PC): Add a 20-bit immediate value to the current PC (Program Counter) value and store the result in a      register.

6. J Type
   This kind of instruction is mainlu used for jump instructions.these instruction allows the program to jump to a spefic memory address
   based on calculated offset.

    | 31      | 20-20     | 19-12   | 11-11      | 10-1 | 0-0    |
    |---------|-----------|---------|------------|------|--------|
    | imm[20] | imm[10:1] | imm[11] | imm[19:12] | rd   | opcode |

- imm[20]: Immediate value, single bit, representing bit 20 of the immediate.
- imm[10:1]: Immediate value, ten bits, representing bits 10 through 1 of the immediate.
- imm[11]: Immediate value, single bit, representing bit 11 of the immediate.
- imm[19:12]: Immediate value, eight bits, representing bits 19 through 12 of the immediate.
- rd: Destination register, five bits, specifying the destination register where the result of the operation is stored.
- opcode: Operation code, seven bits, specifying the type of instruction (e.g., jump).

  **Here's a brief summary of the "J" Type instruction set:**
- JAL (Jump and Link): Jump to a target address and link (store the return address) into a register.
- JALR (Jump and Link Register): Jump to a target address with a register offset and link (store the return address) into a register.
  These function are used for implementing function calls and handling control flows in programs.
  
    
  
                              
