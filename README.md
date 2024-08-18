# ASIC_Class_Design

# Software Tools:
GCC (GNU Compiler Collection)
RISC-V GNU Compiler Toolchain
Spike RISC-V Simulator
Ubuntu OS

# ASSIGNMENT_1
Write a C Program and compile it using the GCC compiler to get Output O0

*Step 1:- Download leafpad editor in the terminal by using the sudo apt command.

![1](https://github.com/user-attachments/assets/6f0be82b-e482-4e3a-b4db-8a6c28a0a823)

*Step 2:-Open a new file in the leafpad editor and write the desired c program and save it.

![2](https://github.com/user-attachments/assets/fcc05254-2243-4cd4-a03b-1f97af6937da)

*step 3:- After saving the file compile it using the GCC Compiler
* Step 4:- Print the output of the code O0.
![3](https://github.com/user-attachments/assets/c57aae7c-1296-434d-a0c9-9b0382f98413)

 # ASSIGNMENT_2

To compile and verify the c code on the riscv compiler and verifying the number of lines in the assembly language code manually

*step 1:-Compiling the c code on the RISCV compiler

#include<stdio.h>
int main()
{
int i,sum=0,n=57;
for(i=0;i<=n;i++)
{
sum+=i;
}
printf("The Sum of the numbers from 1 to %d is %d ",n ,sum);
return 0;
}
Screenshots of the compiled result:-
![ 1](https://github.com/user-attachments/assets/35fa19ba-1ae5-456c-88a5-548be7b1679e)
![W2](https://github.com/user-attachments/assets/cbcb37f0-2842-43d5-8d3b-000fc5fd6d4f)
step 2:- Get the assembly language code for the given c file
Once we get the assembly language code we then verify the number of addresses in the code by subtracting the address next to the last line of the code with the first address and dividing the same by 4 since 4 bytes of data is used by each address line.
![Wha4](https://github.com/user-attachments/assets/72efa356-7306-4dcc-98de-1b68e8c6c314)
