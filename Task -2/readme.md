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
   

     31       25 24       20 19       15 14       12 11        7 6  0
  +----------+----------+----------+----------+----------+----------+
  |  funct7  |   rs2    |   rs1    |   funct3 |   rd     |  opcode  
  +----------+----------+----------+----------+----------+----------+

   - funct7(7 bits) :- it specifies the operatio code of instruction.
   - rs2 (5 bit) :- this field indicates the second source register used by the instruction.
   - rs1 (5 bit) :- source register 1 that indicates the first source register used by the instruction.
   - funct3 (3 bit) :- it specifies teh specific operation within the opcode category.
   - rd (5 bit) :- This field indicates the destination register where the result of the operation is stored.
   - opcode(7 bits) :- it specifies the operatio code of instruction.

  3. I Tyype
     The I type format is used for immediate arithmetic/logical instruction and loads.
     
     
    31                  20 19   15 14     12 11        7 6         0
  +----------+----------+----------+----------+----------+----------+
  |  imm[11:0]          |   rs1    |  funct3 |   rd     |  opcode   
  +----------+----------+----------+----------+----------+----------+


  - imm (12 bit) :-This field contains a 12-bit immediate value, sign-extended to   32 bits, which is used as an operand in the instruction.
  - rs1: Source register 1. This field indicates the source register used by the instruction.
  - funct3: Function code 3. This field specifies the specific operation within the opcode category.
  - rd:  This field indicates the destination register where the result of the operation is stored.
  - opcode: This field specifies the operation code for the instruction.




   
   

    
  
                              
