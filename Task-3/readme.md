# Compiled C Code : sum of number from 1 to n 

step 1: command used in terminal window
```bash
  sudo snap install leafpad
  leafpad sum1tn.c &
  gcc sum1tn.c
  ./a.out
```
![alt text](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/cc4bbb49-180f-44e3-8ffe-08d3d88cdfcf)

![alt text](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/1d0c4000-35fa-440b-abe0-90ae3c4007eb)

step 2: RISCV Objdump

objdump is a utility that display infromation about object files .object files are intermediate files which are generated by compliers during compliation process.when we run 'objdump' on a riscv object file,it provies variosu information about object file such as disassembly.

Disassembly : it is used to disassemble the machine code in object file and makes assembly code in human readable format.
so , objdump is a vdery valuable tool fro inspecting and analyzing object file in RISCV ecosystem.

```bash
cat sum1tn.c
```
here "cat" command is used to display the content presents inside source file(.c file) without opening it an editor.

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/76bd83c4-f183-4340-80fb-b81fafdd2867)

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/4fac95aa-a3e6-4be5-b7de-1d7f5dba2159)

now here we are going to inspect and ananlyse the O1 level for understanding the assembly code of main function .

**1. "O1" level :** 

To do this , we need to open new terminal.
```bash
riscv64-unknown-elf-objdump -d sum1tn.0
```
it will create assembly instrution of object file.
![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/1f9a9b14-736b-469a-bedd-d7a903df2b1a)

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/75e0f451-639b-45cf-885b-b3042fdeb3e5)

next we need to search for assembly instruction for main function in source file.for this we need to type command :
![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/4047463c-12a3-4e5a-b58d-fa8ae5173b11)

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/a679ee0d-05d2-47e5-80d2-18d876b7570f)

```bash
/main
```
![task3_cmd5_main](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/69784a3d-9279-40ce-88d7-0a510ffb2b0c)


here ,inside main instruction: 

- first instruction :10184
- second instruction: 100188
- last instruction :101a8

here every insrction is incremnted by 4 . so when we take difrence of first and last instrction (101a8-10184 =24 ) and divided by incrementing factor 4 , we get total 9 instruction. which we can count from above snapshots .

similary we have to inspect for "Ofast" level in riscv compiler. we will get similar results as we did for "O1" level.

**2. "Ofast" level :** 

 ![task3_cmd6_Ofast_main](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/3790ace2-fabb-4c3e-bfae-149177338cdc)
open a new command terminal , and type following command to get assembly instruction.

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/1b8e4832-5192-4c31-90f0-10ab4c753cc0)

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/5229b3ea-b932-4e2b-a845-91b6f833177e)



To enter into main fucntion instruction assembly code , type following command in terminal.

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/ac6b8a24-d50e-488e-8b01-5a7b56013ff2)

![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/69d9663a-ab56-4c59-94ac-430d0f909e0f)

```bash
/main
```
![image](https://github.com/ranjeet8989/VSDsquadron-mini-internship/assets/84927691/5c008e64-ee13-4ae8-92ac-478602b7643f)







 

 
                                   













