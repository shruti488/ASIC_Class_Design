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

# ASSINGMENT -6
Introduction to TL-Verilog and Makerchip:

Makerchip is a web-based platform that simplifies digital circuit design and prototyping by providing tools for simulation and testing directly in the browser. It supports Hardware Description Languages like Verilog and SystemVerilog, making it ideal for both educational purposes and collaborative projects. With its user-friendly interface and integrated resources, Makerchip facilitates easy design, debugging, and sharing of digital systems.
TL-Verilog extends Verilog by adding advanced features specifically for creating and managing testbenches, making it easier to write, organize, and execute verification tests. It improves the process of checking hardware designs with enhanced support for assertions and functional coverage, thus streamlining the verification workflow an d helping engineers ensure that their designs function correctly.

1: COMBINATIONAL LOGIC:-

A combinational circuit is a digital circuit where the output is determined solely by the current inputs, without any memory or past input history. It uses logic gates (like AND, OR, NOT) to perform operations, and the output is produced instantly based on the input values.


A-> INVERTER

![](https://github.com/user-attachments/assets/f477ccb4-e534-49db-b9df-7a9562a3d004)

B-> OR 

![](https://github.com/user-attachments/assets/6621f6cf-7e38-444a-8a13-dcf378e04609)

C-> MULTIPEXER

![mux](https://github.com/user-attachments/assets/f7e4a12d-f1db-4493-bce7-c4fa79c615d1)

# SEQUENTIOAL LOGIC

Sequential logic circuits are digital circuits where the output depends on both the current inputs and the history of past inputs, due to the presence of memory elements like flip-flops or latches. These circuits often use a clock signal to synchronize state changes, ensuring that the circuit's state is updated at specific intervals. This ability to "remember" past inputs distinguishes sequential logic from combinational logic, where the output is determined solely by the current inputs.

A-> SEQUENTIAL CALCULATOR

![](https://github.com/user-attachments/assets/96fb3960-eca1-43d4-bd68-f1445721c517)

B-> FIBONACCI SERIES

![](https://github.com/user-attachments/assets/040d3fb3-5bfb-4152-9376-cb144662ccff)

# PIPELININIG 

Pipelining is a technique used to increase processing efficiency by dividing tasks into stages, allowing multiple tasks to be processed simultaneously at different stages. It's commonly used in CPUs to speed up instruction execution by processing several instructions in parallel.

A-> FIBNOCCI SERIES

![pipe](https://github.com/user-attachments/assets/945e58b7-70a4-47ad-b2f6-64c7e750cafa)

B-> CYCLIC CALCULATOR

![](https://github.com/user-attachments/assets/3239b359-b0fc-4a57-8bfa-6f6f1d95af20)

# VALIDITY

A-> CALCULATOR

![](https://github.com/user-attachments/assets/dcbd24e1-1d73-429e-b15b-450da77c9931)

B-> TOTAL CYCLIC CALCULATOR

![](https://github.com/user-attachments/assets/ad49702c-269e-4282-9826-5f09d0defef2)
