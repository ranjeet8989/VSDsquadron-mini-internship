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


  





   
   

    
  
                              
