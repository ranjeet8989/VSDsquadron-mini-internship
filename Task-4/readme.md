# SPIKE Simulator Introduction :

spike is a RISCV ISA C++ simulator tool ,primarily used for simulation of riscv processor assembly code.it provides full system simulation or proxied simulation.
it managhe to assist strating point for running riscv programms on a RISCV Target.spike simulator possesses some of the unique feature which incorporteas as :

- Multiple ISA : RISCV32I /RISCV64I
- Debugging & Testing : used primarily for testing and debugging and testing the code.
- Multiple CPU support
- JTAG support
- Integration with other development tools.

# SPIKE Simulation with -Ofast :

  here the '-Ofast' is a compiler flag ,generally used with "gcc tool" for greater level of optimisation of code.it can be used only with compiler. spike itslef a 
  simulator not a complier that simultes the assembly code of c programms. so optimisation can be determined during compilation time (gcc).once the code is compiled
  into machine code with desired optimisation level then we can go for simulation with spike simulator .

  1. create C programme on leafpad editor and simulate it using spike simulatro in **Terminal window = 1**
     
  ```bash
  leafpad sumtn.c
  gcc sum1tn.c &
  ./a.out
  riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1tn.o sum1tn.c
  spike pk sum1tn.o
  ```
  output using riscv gcc comiler.

  ![task4_01](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/f8780d87-9b19-498b-9dec-036a408cd76b)
  output using spike simulator
  ![task4_1](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/3f801948-33ed-4fb6-97f8-59520b0a0a1f)

  2.open another terminal for objdump: **Terminal window=2**
    
    run following commands in terminal window=2
    
  ```bash
  riscv64-unknown-elf-objdump -d sum1tn.o |less
  /main
  ```
  ![task4_2 0_fileformt](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/b5c89b41-e317-4536-9f4e-121754171eb6)

  3. open debugger mode : **Terminal window=1**
     
     run following command in terminal
     
     ```bash
     spike -d pk sum1tn.o
     until pc 0 100b0
     ```
  ![task4_61_spdcremnt](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/5f242fc9-e22a-45f6-986c-c9250d29c1ba)


  # SPIKE Simulation with -O1 :

  The "-O1" optimisation level is a compiler flag used to provide minimal optimisation which is very faster than unoptimised code.it imprvoes the performance of code 
  without  increasing the code size.it provides relatively easy debugging compared to higher optimsation level compiler flag.

  1. create C programme  and simulate it using spike simulatro in: **Terminal window=1**
     
      ```bash
      leafpad sum1tn.c
      gcc sum1tn.c &
      ./a.out
      riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1tn.o sum1tn.c
      spike pk sum1tn.o
      
      ```
      
       ![task4_7_O1_](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/8936321a-40c7-4618-ac07-7bce0d695435)
     

  2.open another terminal for objdump: **Terminal window=2**
    
    run following commands in terminal window=2
    
          ```bash
          riscv64-unknown-elf-objdump -d sum1tn.o |less
          /main
          ```
      
  ![task4_7_O1_formt](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/cc03cb31-2fd7-4357-95af-a0455aa934ec)

  3. open debugger mode : **Terminal window= 1**
     
     run following command in terminal
     
           ```bash
           spike -d pk sum.o
           until pc 0 100b0
           ```
       
  ![task4_8_O1_sp](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/e9a8294d-943e-4f43-badd-dfb4e4f0c7c5)

     here , if we subtract decimal -16 value which is 10 in hexadecimal value we get new modified value for sp register .
     0x0000003ffffffb50 - 10(Hex) =0x0000003ffffffb40
     16(Decimal)=10(Hex).


      

      
      

  



  
  
  


  
