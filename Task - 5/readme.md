# 1. RISCV32I CORE HARDWARE IMPLEMENTATION :-

Here, we have implemtned the RISCV32I in hardware descriotion languaeg language (HDL) Netlist  using GTK EDA tool and verify the function corrctness of each instruction
that we perfromed with riscv gnu simulator "spike".

**Introduction on RISCV32I** :-
<div style="text-align: justify"> 
RISC32I is a 32 bit instruction set architecture (ISA) in base integer format. here " I " refers to integer register and every instruction like computational instructions,load instructions,store instructions & control instructions are in integer format stored in registers memory.it is very similar to earleir risc processors.it provides a 
variabel length instruction encoding. this base integer instruction format is very much restricted to minimal set of instrction.such restriction provides resonable target 
for compilers,assemblers,linkers and operating system.This complete infrastructeure of riscv ISA is under "unprivileged ISA" where a user  can execute operation such as 
airthemteic operation, logical operation, memory access instruction and other common operation.unprivileged instruction are those instruction that can be executed by ordianry
applcation programs without requiring special privileges.
</div>

Each base integer ISA is characterised by :-

  - width of integer registers.
  - size of address space.
  - numebr of integer registers.

**Block Design of RISCV32I** 

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/9212e6de-f5be-4e82-ba83-178ffea8b4e7)


# 2. Instruction Set Of RISCV32I:-

| Instruction Type | RISCV32I Instruction  | Function                                         |
|------------------|-----------------------|--------------------------------------------------|
| Computational    | add                   | Perform addition                                 |
|                  | addi                  | Perform addition with immediate value            |
|                  | sub                   | Perform subtraction                              |
|                  | slr                   | Perform logical right shift                      |
|                  | sll                   | Perform logical left shift                       |
|                  | and                   | Perform bitwise AND                              |
|                  | or                    | Perform bitwise OR                               |
|                  | xor                   | Perform bitwise XOR                              |
|                  | slt                   | Set if less than                                 |
| Control Flow     | beq                   | Branch if equal                                  |
|                  | bne                   | Branch if not equal                              |
|                  |                       |                                                  |
| Memory Access    | lw                    | Load a 32-bit word into the destination register |
|                  | sw                    | Store a 32-bit word                              |

# 3. Terminal Command for GTK wave:-

   
  ![task5_1](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/e1da3b51-f77f-4caa-936a-df429bd6cc0f)

  ![task5_2](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/4358ffc9-1d16-4fe9-93d5-6d487be6fb2e)

# 4. Functional Simulation waveform for RV32I Instruction:-

- add r6,r2,r1
  
![task5_3_add](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/5a689ffe-8898-4b3a-ae4b-a0d208b4760f)
     
- sub r7,r1,r2
  
![task5_4_sub](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/434d3a63-a67e-4f90-b9b5-f1c20e9e4702)

- and r8,r1,r3
  
![task5_5_and](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/3f5b7439-5ec9-41e7-adb5-bfa9ad021e51)

- or r9,r2,r5
  
![task5_6_or](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/e1f58928-1aa5-41d3-9cbb-93223f912c2c)

- xor r10,r1,r4

![task5_7_xor](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/ee83d15a-b06b-475c-8993-1c151cabdfb7)

- slt r11,r2,r4

![task5_7_slt](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/959c0ae6-374c-4586-b721-8e35ddf394e3)

- addi r12,r4,5

![task5_8_addi](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/b5254793-335a-49df-b2f7-fec0700e9a8e)

- sw r3,r1,2

![task5_9_sw](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/49eba861-930a-43af-988a-26e98c90afb5)

- lw r13,r1,2

![task5_10_lw](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/3ff50e60-96f1-44fe-94aa-0d57aa10083c)

- beq r0,r0,15

![task5_10_beq](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/47d55e03-113c-4f37-9adf-5f8c858c629d)

- add r14,r2,r2

![task5_12_add](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/b46cae5b-539a-4ef3-b50b-b2c22208c5c1)

- Full five-stage instruction pipeline with PC increment waveform.

![task5_13_pipeline](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/0363997f-4e70-4b49-84ce-e7884e224301)
















