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

# ASSIGNMENT -3
Determine the output of the C program using the RISC-V Compiler using Spike simulator, and then debug the code
Step 1: Compile sum1ton.c using RISCV Compiler using the command given below

riscv64-unknown-elf-gcc -O1 -mabi=lp64-march=rv64i -o sum1ton.o  sum1ton.c

Step 2: Now we have compiled our program using RISCV compiler and we need to run in order to get the output similar to the ./a.out we do using gcc compiler. To do that use Spike Simulator and type the following command given below

spike pk sum1ton.o
![](https://github.com/user-attachments/assets/38dfb370-afc0-476f-bdae-264b855160ed)

Debugging the Assembly Code

![](https://github.com/user-attachments/assets/ba73f761-536a-4d88-ac4d-f63eddf2544d)

The assembly code of Ofast

![3](https://github.com/user-attachments/assets/9cc34141-90a6-4a6b-9737-85829b86fb92)

To debug the assembly code of your compiled C program using the Spike simulator, follow these steps:

spike -d pk sum1ton.o

We will let the Spike debugger run until it reaches the 100b0 instruction within the main function by running the command given below. From there, we will proceed with manual debugging, checking the a2 register before and after execution.To move on to next instruction press Enter

until pc 0 100b0

Similarly we can apply the same logic for Ofast code

until pc 0 100bo

To check a registers Value type the following command

reg 0 a2

The following are the initial contents of the stack pointer

![](https://github.com/user-attachments/assets/f8035feb-34d9-45df-988d-039e245ad9cb)

In the assembly code we can see that the value of the stack pointer is being reduced by 10 in hexadecimal we is equivalent to being reduced by 16 in decimal notation
After running the first line of the code the contents of the stack pointer get modified and we get the follwoing result

![](https://github.com/user-attachments/assets/2de108ac-7905-4068-b458-65656e9fcee7)

Similarly for the register a0 we observe the following initial and final contents [ O-fast]
reg 0 a0

![66](https://github.com/user-attachments/assets/8ce8fd15-acfc-4631-9dbf-d6a455d541b1)


Similarly we can do the same for all the other instructions in the code and find out the contents in the respective addressing locations and their updated values once we execute the lines in the debugger.

# ASSIGNMENT -5

Selecting and Compiling a Application using GCC and RISC-V GCC

# APPLICATION NAME - PRIME NUMBER CHECKER

#include <stdio.h>
#include <stdbool.h>

bool is_prime(int n) {
    if (n <= 1) return false;
    for (int i = 2; i <= n / 2; i++) {
        if (n % i == 0) return false;
    }
    return true;
}

int main() {
    int num;
    printf("Enter an integer: ");
    scanf("%d", &num);

    if (is_prime(num))
        printf("%d is a prime number.\n", num);
    else
        printf("%d is not a prime number.\n", num);

    return 0;
}

![](https://github.com/user-attachments/assets/0e587bbf-1335-40ee-95a6-9c21578b643d)

![  k](https://github.com/user-attachments/assets/742afb0e-10e9-498d-ab2d-c3017ceaef7d)



# ASSINGMENT -6

# Introduction to TL-Verilog and Makerchip:

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

#  Basic RISC-V CPU Micro-architecture

 Basic RISC-V CPU Micro-architecture
 
 ![1111](https://github.com/user-attachments/assets/e31e8257-f2f5-4abb-a512-119c6bc69f34)

1: Program Counter: The Program Counter (PC) is a critical component in a RISC-V CPU (and any CPU in general), responsible for keeping track of the address of the next instruction to be executed. Understanding the role and implementation of the PC is fundamental when designing or working with a RISC-V CPU.
2: Instruction Fetch: Instruction fetch is the first stage in the instruction execution cycle of a RISC-V CPU. It involves retrieving the instruction pointed to by the Program Counter (PC) from memory so that it can be decoded and executed in subsequent stages.

3: Instruction Decode: Instruction decode is the second stage in the instruction execution cycle of a RISC-V CPU. After an instruction is fetched from memory, it needs to be interpreted, or "decoded," to understand what operation is to be performed and which operands are involved. The decoding process involves breaking down the binary instruction into its constituent fields, such as opcode, source registers, destination registers, and immediate values. 
4: ALU: The Arithmetic Logic Unit (ALU) in a RISC-V CPU is a key component responsible for performing arithmetic and logical operations. The ALU receives inputs from the register file or immediate values from instructions and produces results that are either stored back into registers, used for branching decisions, or forwarded to other components like memory.

# PROGRAM COUNTER

![4program counter](https://github.com/user-attachments/assets/0e8160f6-8d9f-49b0-8691-f1e5cb728c38)

# RISCV Core Implementation
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV

   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      
      
      @0
         $clk_Shr = *clk;
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 1'b0 : >>1$taken_branch ? >>1$br_tgt_pc : >>1$pc + 32'd4;
         
      @1 
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $inst[31:0] = $imem_rd_data[31:0]; 
         
         $is_i_instr = $inst[6:2] ==? 5'b0000x ||
                       $inst[6:2] ==? 5'b001x0 ||
                       $inst[6:2] ==? 5'b11001;
                       
         
         $is_u_instr = $inst[6:2] ==? 5'b0x101;
         
         $is_r_instr = $inst[6:2] ==? 5'b01011 ||
                       $inst[6:2] ==? 5'b011x0 ||
                       $inst[6:2] ==? 5'b10100;
         
         $is_b_instr = $inst[6:2] ==? 5'b11000;
         
         $is_j_instr = $inst[6:2] ==? 5'b11011;
         
         $is_s_instr = $inst[6:2] ==? 5'b0100x;
         
         
         $imm[31:0] = $is_i_instr ? {{21{$inst[31]}}, $inst[30:20]} :
                      $is_s_instr ? {{21{$inst[31]}}, $inst[30:25], $inst[11:8], $inst[7]} :
                      $is_b_instr ? {{20{$inst[31]}}, $inst[7], $inst[30:25], $inst[11:8], 1'b0} :
                      $is_u_instr ? {$inst[31], $inst[30:20], $inst[19:12], 12'b0} :
                      $is_j_instr ? {{12{$inst[31]}}, $inst[19:12], $inst[20], $inst[30:21], 1'b0} :
                                    32'b0;
         
         $rs1_use = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_use
            $rs1[4:0] = $inst[19:15];
         
         $rs2_use = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_use
            $rs2[4:0] = $inst[24:20];
            
         $funct3_use = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_use
            $funct3[2:0] = $inst[14:12];
            
         $funct7_use = $is_r_instr ;
         ?$funct7_use
            $funct7[6:0] = $inst[31:25];
            
         $rd_use = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_use
            $rd[4:0] = $inst[11:7];
         
         $opcode[6:0] = $inst;
         
         $dec_bits [10:0] = {$funct7[5], $funct3, $opcode};
         
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         
         //Register Read 
         $rf_rd_en1 = $rs1_use;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_en2 = $rs2_use;
         $rf_rd_index2[4:0] = $rs2;
         
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
         
       
         
         //ALU
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;
         
         //Register File Write 
         
         $rf_wr_en = $rd_use;
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $rd == 0 ? 0 : $result;
         
         //Branch Instructions
         
         $taken_branch = $is_beq ? ($src1_value == $src2_value):
                         $is_bne ? ($src1_value != $src2_value):
                         $is_blt ? (($src1_value < $src2_value)^($src1_value[31] != $src2_value[31])):
                         $is_bge ? (($src1_value >= $src2_value)^($src1_value[31] != $src2_value[31])):
                         $is_bltu ? ($src1_value < $src2_value):
                         $is_bgeu ? ($src1_value >= $src2_value):
                                    1'b0;
         `BOGUS_USE($taken_branch)
         $br_tgt_pc[31:0] = $pc + $imm;
         
         //Testbench
         *passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9) ;
      // YOUR CODE HERE
      // ...

      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule

![complte core risc](https://github.com/user-attachments/assets/3190f2d5-382e-48ff-95f8-3ba3b10ef68e)

# Complete Pipelined RISCV core

\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV

   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      
      
      @0
         $clk_shr = *clk;
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 :
                     >>3$valid_taken_branch ? >>3$br_tgt_pc :
                     >>3$valid_load ? >>3$inc_pc : 
                     (>>3$valid_jump && >>3$is_jal) ? >>3$br_tgt_pc :
                     (>>3$valid_jump && >>3$is_jalr) ? >>3$jalr_tgt_pc :
                     >>1$inc_pc;
      
      @1 
         $inc_pc = $pc + 32'd4;
         $imem_rd_en = !>>1$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
      
      
      
      @3 
          //valid 
         $valid = !(>>1$valid_taken_branch || >>2$valid_taken_branch || >>1$valid_load || >>2$valid_load 
                    || >>1$valid_jump || >>2$valid_jump) ;
                    
         $valid_load = $valid && $is_load ;
         $valid_jump = $valid && $is_load;
      
      
         
      @1   
         $inst[31:0] = $imem_rd_data[31:0]; 
         
         // Assigning instruction type signal i.e. decoding instruction type
         $is_i_instr = $inst[6:2] ==? 5'b0000x ||
                       $inst[6:2] ==? 5'b001x0 ||
                       $inst[6:2] ==? 5'b11001;
                       
         
         $is_u_instr = $inst[6:2] ==? 5'b0x101;
         
         $is_r_instr = $inst[6:2] ==? 5'b01011 ||
                       $inst[6:2] ==? 5'b011x0 ||
                       $inst[6:2] ==? 5'b10100;
         
         $is_b_instr = $inst[6:2] ==? 5'b11000;
         
         $is_j_instr = $inst[6:2] ==? 5'b11011;
         
         $is_s_instr = $inst[6:2] ==? 5'b0100x;
         
         //Decoding Immediate 
         $imm[31:0] = $is_i_instr ? {{21{$inst[31]}}, $inst[30:20]} :
                      $is_s_instr ? {{21{$inst[31]}}, $inst[30:25], $inst[11:8], $inst[7]} :
                      $is_b_instr ? {{20{$inst[31]}}, $inst[7], $inst[30:25], $inst[11:8], 1'b0} :
                      $is_u_instr ? {$inst[31], $inst[30:20], $inst[19:12], 12'b0} :
                      $is_j_instr ? {{12{$inst[31]}}, $inst[19:12], $inst[20], $inst[30:21], 1'b0} :
                                    32'b0;
         $opcode[6:0] = $inst[6:0];
          
          
         $rs1_use = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_use
            $rs1[4:0] = $inst[19:15];
         
         $rs2_use = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_use
            $rs2[4:0] = $inst[24:20];
            
         $funct3_use = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_use
            $funct3[2:0] = $inst[14:12];
            
         $funct7_use = $is_r_instr ;
         ?$funct7_use
            $funct7[6:0] = $inst[31:25];
            
         $rd_use = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_use
            $rd[4:0] = $inst[11:7];
         
        
         
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_load = $dec_bits ==? 11'bx_xxx_0000011;
         $is_sb = $dec_bits ==? 11'bx_000_0100011;
         $is_sh = $dec_bits ==? 11'bx_001_0100011;
         $is_sw = $dec_bits ==? 11'bx_010_0100011;
         $is_slti = $dec_bits ==? 11'bx_010_0010011;
         $is_sltiu = $dec_bits ==? 11'bx_011_0010011;
         $is_xori = $dec_bits ==? 11'bx_100_0010011;
         $is_ori = $dec_bits ==? 11'bx_110_0010011;
         $is_andi = $dec_bits ==? 11'bx_111_0010011;
         $is_slli = $dec_bits ==? 11'b0_001_0010011;
         $is_srli = $dec_bits ==? 11'b0_101_0010011;
         $is_srai = $dec_bits ==? 11'b1_101_0010011;
         $is_sub = $dec_bits ==? 11'b1_000_0110011;
         $is_sll = $dec_bits ==? 11'b0_001_0110011;
         $is_slt = $dec_bits ==? 11'b0_010_0110011;
         $is_sltu = $dec_bits ==? 11'b0_011_0110011;
         $is_xor = $dec_bits ==? 11'b0_100_0110011;
         $is_srl = $dec_bits ==? 11'b0_101_0110011;
         $is_sra = $dec_bits ==? 11'b1_101_0110011;
         $is_or = $dec_bits ==? 11'b0_110_0110011;
         $is_and = $dec_bits ==? 11'b0_111_0110011;
         $is_lui = $dec_bits ==? 11'bx_xxx_0110111;
         $is_auipc = $dec_bits ==? 11'bx_xxx_0010111;
         $is_jal = $dec_bits ==? 11'bx_xxx_1101111;
         $is_jalr = $dec_bits ==? 11'bx_000_1100111;
         $is_jump = $is_jal || $is_jalr ;
         
         `BOGUS_USE($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add) 
         
         
      @2
         //Register Read 
         $rf_rd_en1 = $rs1_use && >>2$result;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_en2 = $rs2_use && >>2$result;
         $rf_rd_index2[4:0] = $rs2;
         
         //$src1_value[31:0] = $rf_rd_data1;
         //$src2_value[31:0] = $rf_rd_data2;
         
         //Branching Criteria for Program Counter 
         $br_tgt_pc[31:0] = $pc + $imm;
         
         
         
         //source to alu assigned with o/p of read register
         $src1_value[31:0] = 
              (>>1$rf_wr_index == $rf_rd_index1) && >>1$rf_wr_en ?
                 >>1$result :
                  $rf_rd_data1;
         $src2_value[31:0] = 
              (>>1$rf_wr_index == $rf_rd_index2) && >>1$rf_wr_en ?
                 >>1$result :
                   $rf_rd_data2;
      
         //Data Memory Read - Write
      @4
         $dmem_wr_en = $is_s_instr && $valid ;
         $dmem_addr[3:0] = $result[5:2] ;
         $dmem_wr_data[31:0] = $src2_value ;
         $dmem_rd_en = $is_load ;
         
      @4 
         //LOAD DATA
         $ld_data[31:0] = $dmem_rd_data ;
      
      @3
         
         $jalr_tgt_pc[31:0] = $src1_value + $imm ;  
         
         
      @3   
         //ALU
         
         $sltu_rslt[31:0] = $src1_value < $src2_value ;
         $sltiu_rslt[31:0]  = $src1_value < $imm ;
         
         
         $result[31:0] = $is_addi ? $src1_value + $imm :
              $is_add ? $src1_value + $src2_value :
              $is_andi ? $src1_value & $imm :
              $is_ori  ? $src1_value | $imm :
              $is_xori ? $src1_value ^ $imm :
              $is_slli ? $src1_value << $imm[5:0] :
              $is_srli ? $src1_value >> $imm[5:0] :
              $is_and ? $src1_value & $src2_value :
              $is_or ? $src1_value | $src2_value :
              $is_xor ? $src1_value ^ $src2_value :
              $is_sub ? $src1_value - $src2_value :
              $is_sll ? $src1_value << $src2_value[4:0] :
              $is_srl ? $src1_value >> $src2_value[4:0] :
              $is_sltu ? $src1_value < $src2_value :
              $is_sltiu ? $src1_value < $imm :
              $is_lui ? {$imm[31:12], 12'b0} :
              $is_auipc ? $pc + $imm : 
              $is_jal ? $pc + 32'd4 :
              $is_jalr ? $pc + 32'd4 :
              $is_srai ? {{32{$src1_value[31]}}, $src1_value} >> $imm[4:0] :
              $is_slt ? ($src1_value[31] == $src2_value[31]) ? $sltu_rslt : {31'b0, $src1_value[31]} :
              $is_slti ? ($src1_value[31] == $imm[31]) ? $sltiu_rslt : {31'b0, $src1_value[31]} :
              $is_sra ? {{32{$src1_value[31]}}, $src1_value} >> $src2_value[4:0] :
              $is_load || $is_s_instr ? $src1_value + $imm :
              32'bx ;
      @3
         //Register File Write 
         
         $rf_wr_en = $rd_use && $rd != 5'b0 && $valid || >>2$valid_load;
         $rf_wr_index[4:0] = >>2$valid_load ? >>2$rd : $rd;
         $rf_wr_data[31:0] = >>2$valid_load ? >>2$ld_data :  $result;
         
         //Branch Instructions
         
         $taken_branch = $is_beq ? ($src1_value == $src2_value):
                         $is_bne ? ($src1_value != $src2_value):
                         $is_blt ? (($src1_value < $src2_value)^($src1_value[31] != $src2_value[31])):
                         $is_bge ? (($src1_value >= $src2_value)^($src1_value[31] != $src2_value[31])):
                         $is_bltu ? ($src1_value < $src2_value):
                         $is_bgeu ? ($src1_value >= $src2_value):
                                    1'b0;
          
          
         // Condition for Invalid Instruction                          
         $valid_taken_branch = $valid && $taken_branch;
         
         
       
         
         `BOGUS_USE($taken_branch)
        
         
         //Testbench
         *passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9) ;
      // YOUR CODE HERE
      // ...

      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@2, @3)  // Args: (read stage, write stage) - if equal, no register bypass is required
      m4+dmem(@4)    // Args: (read/write stage)

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule

   ![coode](https://github.com/user-attachments/assets/0f9bd1cc-c47c-48e0-9146-f3dc3381f98e)

![](https://github.com/user-attachments/assets/fa537073-dca2-468f-85a9-b3e06362bbfd)

![](https://github.com/user-attachments/assets/40cd16e6-de43-4e00-b9c8-2ded4a180746)

![](https://github.com/user-attachments/assets/80e44645-3fc2-4513-b16f-ca42120e98da)

# ASSIGNMENT 7

# Conversion from TLV into Verilog using Sandpiper-SaaS compiler.Following the conversion, pre-synthesis simulations will be conducted using the GTKWave simulator to verify the design.

The RISC-V processor was originally designed using TL-Verilog within the Makerchip IDE. To deploy this design onto an FPGA, it was necessary to convert the TL-Verilog code into standard Verilog. This conversion was successfully carried out using the Sandpiper-SaaS compiler, which facilitated the transition from high-level TL-Verilog to the more widely used Verilog language, suitable for FPGA implementation. After the conversion, pre-synthesis simulations will be performed using the GTKWave simulator to thoroughly verify the functionality and correctness of the design before proceeding to the synthesis and hardware deployment stages. These simulations are crucial for ensuring that the design behaves as expected in a real hardware environment.

STEP 1: Install sandpiper-sass using following command:

pip3 install pyyaml click sandpiper-saas

STEP2:Clone the Github and go to VSDbabySoc folder

git clone https://github.com/manili/VSDBabySoC.git
cd VSDBabySoc 
![B](https://github.com/user-attachments/assets/359abc3b-6d92-4e8d-80ae-d9ae50d4df03)

STEP3: Replace the following code in src/module with the rvmyth.tlv given and also change the testbench according to our makerchip code.
![CC](https://github.com/user-attachments/assets/72e41672-af3e-4326-a77a-f245b4c36899)

STEP 4: Now run the following command to convert the code.

sandpiper-saas -i /home/vsduser/VSDBabySoC/src/module/shr_rvmyth.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir /home/vsduser/VSDBabySoC/src/module/

![1F](https://github.com/user-attachments/assets/bd84cb50-14ac-4e32-bea0-ed8d07ce8cfd)

 step 5:Now create the pre_synth_sim.vcd by running the following command.

make pre_synth_sim

STEP 6: To compile and simulate RISC-V design run the following code:

iverilog -o output/pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module
cd output
./pre_synth_sim.vcd

STEP 7: To open the Simulation file in gtkwave tool, run the following command.
gtkwave pre_synth_sim.vcd

![2F](https://github.com/user-attachments/assets/1ab4ee35-b830-4cef-8f0b-6b92652c49d6)

 # Waveforms from GTKwave platform by running .v file after conversion
Clk,Reset, Waveforms in one

![f](https://github.com/user-attachments/assets/327b68c8-8896-4ce8-8cdc-863c675f6fed)

![](https://github.com/user-attachments/assets/3d346150-86cf-4946-bb19-8f436e76df97)


# ASSIGNMENT -8

# Integrating PLL, riscv core and DAC on babySOC and verifying its output.

 this task we have used a PLL, Riscv core and DAC. Input to PLL is a low frequency signal coming from the crystal oscillators of SOC. PLL increases the frquency of input signal and gives it as input to the riscv core. The riscv core gives a 10 bit digital output which is gurther given to a DAC converter. The output of DAC is an analog signal OUT.We further analyze the ouptut in gtkWave.
VCO_IN is the input to PLL
CLK is the output of PLL
clk_vai is the input of riscv
OUT is the 10 bit output of riscv
OUT is the output of DAC

Here are the commands to do that
Time and date are also dislayed: 


![Screenshot from 2024-09-03 02-02-07](https://github.com/user-attachments/assets/4c98942b-41c1-4a90-8227-9f65168d14e3)

Here is the output of gtkWave

![Screenshot from 2024-09-03 01-57-38](https://github.com/user-attachments/assets/5dedf54c-b809-4198-886d-e9cf5c1750a7)


#ASSIGNMENT - 9

RTL design using Verilog with SKY130 Technology

A simulator is used to confirm that a design meets its specifications by executing the corresponding code. It tracks changes in input signals, and upon any input change, it updates the outputs accordingly. RTL (Register Transfer Level) design refers to the Verilog code that captures the behavior of a digital circuit. To validate this design, a testbench is created and simulated with Icarus Verilog. During this simulation, a VCD (Value Change Dump) file is generated. This file can be examined using GTKWave, a tool that enables users to load, view, and analyze the waveforms produced during the simulation. By inspecting these waveforms, users can investigate signal interactions, confirm timing relationships, and ensure the circuit functions correctly.


![](https://github.com/user-attachments/assets/8cbd88a7-82f2-4e8d-a001-ae995df1315a)

#DAY-1 LAB
![](https://github.com/user-attachments/assets/e18427e1-068c-4d8a-8108-19bb788d9a93)
![](https://github.com/user-attachments/assets/db7695f5-01ee-47a8-a5c3-ca74b7d00f24)
![](https://github.com/user-attachments/assets/a0fd3269-e765-4a41-9115-4991d778d75a)
![](https://github.com/user-attachments/assets/1914487f-9a0c-4194-a795-9bd92bec8684)
![](https://github.com/user-attachments/assets/afc3f23b-45b4-4317-bda8-2ad60d211e82)
![](https://github.com/user-attachments/assets/fd4120d0-b0e8-4505-af18-fd549d022f1a)
![](https://github.com/user-attachments/assets/96e25ae5-fc23-4468-ba71-8d51ccd216bb)
![](https://github.com/user-attachments/assets/1814e00d-508e-431a-9c8e-7c448710259a)
![](https://github.com/user-attachments/assets/f3fd59ad-db80-481f-baf7-adeb8cb92b2d)
![](https://github.com/user-attachments/assets/90f86ccf-e7d8-4e33-94ae-6f3acb85d5a7)
![](https://github.com/user-attachments/assets/96827457-1ba5-4b1e-9cea-9ecbe26ef51f)


#DAY-2 LAB

Yosys Synthesis for Multiple Modules: This tutorial involved the synthesis of a design file that has more than one module.

//Design

module sub_module2 (input a, input b, output y);
	assign y = a | b;
endmodule

module sub_module1 (input a, input b, output y);
	assign y = a&b;
endmodule

module multiple_modules (input a, input b, input c, output y);
	wire net1;
	sub_module1 u1(.a(a),.b(b),.y(net1)); //net1 = a&b
	sub_module2 u2(.a(net1),.b(c),.y(y)); //y = netic,ie y = a&b + c;
endmodule


 yosys
 read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 read_verilog multiple_modules.v
 synth -top multiple_modules
 abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 show
 write_verilog -noattr multiple_modules_netlist.v
 gvim multiple_modules_netlist.v

 //Generated Netlist
module multiple_modules (a, b, c, y);
	input a; wire a;
	input b; wire b;
	input c; wire c;
	wire net1;
	output y; wire y;

	sub_modulel ul (.a(a),.b(b),.y(net1));
	sub_module2 u2 (.a(net1),.b(c),.y (y));
endmodule

module sub_modulel (a, b, y);
	wire _0_;
	wire _1_;
	wire _2_;
	input a; wire a;
	input b; wire b;
	output y; wire y;
	
sky130_fd_sc_hd_and2_0_3_(.A(_1_),.B(_0_),.X(_2_));
		assign _1_ = b;
	assign _0_ = a;
	assign y = _2_;
endmodule

module sub_module2 (a, b, y);
	wire _0_;
	wire _1_;
	wire _2_;
	input a; wire a;
	input b; wire b;
	output y;wire y;

sky130_fd_sc_hd_or2_0_3_ (A(_1_), .B( 0 ), .X( 2 ));
	assign _1_ = b;
	assign _0_ = a;
	assign y = _2_;
endmodule

![](https://github.com/user-attachments/assets/e1b758e3-21cc-4ae3-8273-06db5d8ab558)
![](https://github.com/user-attachments/assets/b1e430d2-8fac-4ac0-8af5-d718f2b63798)
![](https://github.com/user-attachments/assets/fe5bb9f9-da84-48ae-9e63-9e4e411e9cfe)
![](https://github.com/user-attachments/assets/488f1a3c-9c5b-425e-a6bc-39256236ff69)
![](https://github.com/user-attachments/assets/b6dc8c05-48c6-41ed-982a-75db912e6d30)
![](https://github.com/user-attachments/assets/72b6196e-500a-44bb-abf6-c3da6e988d95)
![](https://github.com/user-attachments/assets/3bb7149c-1851-42cd-ab33-aac8ffa07d7b)
![](https://github.com/user-attachments/assets/606080f8-a47e-456f-badf-85edf48fb084)
![](https://github.com/user-attachments/assets/090fc6c8-87e1-450b-9bf7-33c0e4d5191c)
![](https://github.com/user-attachments/assets/ce6e0573-4280-49cd-8c10-5a02bdc0522e)
![](https://github.com/user-attachments/assets/d5b08097-d647-4917-b1e0-6d58aa2c1d0b)
![](https://github.com/user-attachments/assets/10fa6f55-c3c4-449a-8817-e466556cc88a)
![](https://github.com/user-attachments/assets/cae6c807-392a-4ba1-85ac-3272d1633eda)
![](https://github.com/user-attachments/assets/e660403c-0a4a-4d9a-9c06-be7be59b9ae3)
![](https://github.com/user-attachments/assets/a590688f-6f84-41a4-82c3-c009396f2e84)
![](https://github.com/user-attachments/assets/f2692ae8-1a44-4117-a7ee-ef9850296111)

Simulation of D-Flipflop using Iverilog and GTKWave: Performed simulations for 3 types of D-Flipflops - Asynchronous Reset, Asynchronous Set and Synchronous Reset. Asynchronous Reset


![Screenshot from 2024-10-21 23-15-53](https://github.com/user-attachments/assets/46808c82-2036-495e-842c-a7fe963ab500)
![Screenshot from 2024-10-21 23-16-37](https://github.com/user-attachments/assets/39176c49-ad14-474c-94e4-00d8e667f8bb)

Asynchronous Set-

![Screenshot from 2024-10-21 23-34-44](https://github.com/user-attachments/assets/e475d82a-004d-4469-8f7d-0f9c9632c9ed)

![Screenshot from 2024-10-21 23-35-43](https://github.com/user-attachments/assets/4443e8e6-d7d5-4819-ab02-c0dabef6ceb6)

Synthesis of D-Flipflop using Yosys: Synthesized 3 types of D-Flipflops - Asynchronous Reset, Asynchronous Set and Synchronous Reset. Asynchronous Reset

![Screenshot from 2024-10-21 23-40-04](https://github.com/user-attachments/assets/723750a1-112d-4c43-82ba-7c6ce6ec7143)
![Screenshot from 2024-10-21 23-41-23](https://github.com/user-attachments/assets/e372c605-92a6-4d1c-b97d-7849a4e81886)
![Screenshot from 2024-10-21 23-41-39](https://github.com/user-attachments/assets/c89ee32d-4482-4214-b994-4d478cb71845)
![Screenshot from 2024-10-21 23-41-54](https://github.com/user-attachments/assets/d85c6602-ee1c-4de7-b80c-330ccbb34ea8)
![Screenshot from 2024-10-21 23-43-19](https://github.com/user-attachments/assets/febc7b9f-8285-4f22-98d8-4020c91ff222)
![Screenshot from 2024-10-21 23-44-49](https://github.com/user-attachments/assets/c1ef6767-136d-4fb8-9f07-64deff8c0622)
![Screenshot from 2024-10-21 23-45-01](https://github.com/user-attachments/assets/fe82dfd3-4fd0-4fd1-b30e-87dd5778b170)
![Screenshot from 2024-10-21 23-45-15](https://github.com/user-attachments/assets/6a6c3c60-15f0-40b8-919e-d32121e949d1)
![Screenshot from 2024-10-21 23-45-58](https://github.com/user-attachments/assets/5ad6c7f3-292e-4fba-9153-e4ceff312e2e)
![Screenshot from 2024-10-21 23-46-20](https://github.com/user-attachments/assets/688abf7a-f102-4ee2-970c-3b238952767a)
![Screenshot from 2024-10-21 23-47-25](https://github.com/user-attachments/assets/d8883776-d8f5-48c2-b73b-19e950ce5344)
![Screenshot from 2024-10-21 23-48-03](https://github.com/user-attachments/assets/8a643e27-c227-4be9-a45c-b2a2b77a10b2)
![Screenshot from 2024-10-21 23-48-23](https://github.com/user-attachments/assets/084514f9-db89-440a-8ab3-3b8bbad31e22)
![Screenshot from 2024-10-21 23-50-22](https://github.com/user-attachments/assets/f4e117d2-bc1c-42ea-9745-c05b1a541a8f)
![Screenshot from 2024-10-21 23-50-50](https://github.com/user-attachments/assets/b4a882f1-5b7e-496e-af95-c3928cd2607e)
![Screenshot from 2024-10-21 23-51-36](https://github.com/user-attachments/assets/d711d304-eae0-4fd9-97aa-2f1c4ac187de)
![Screenshot from 2024-10-21 23-53-03](https://github.com/user-attachments/assets/86819472-399c-422d-a02c-7930c3087bdb)
![Screenshot from 2024-10-21 23-53-36](https://github.com/user-attachments/assets/4fd042c0-5a05-4f2a-9681-88f3e1b5fe29)
![Screenshot from 2024-10-22 00-00-50](https://github.com/user-attachments/assets/d55dac25-7d0b-4af8-9cdb-cab24f4210ac)
![Screenshot from 2024-10-22 00-01-07](https://github.com/user-attachments/assets/f395c3bd-e18d-4aa8-956e-6d82bd3f8bec)
![Screenshot from 2024-10-22 00-01-20](https://github.com/user-attachments/assets/6bbeb0a0-10e8-4821-8e3d-86c2f61d42e9)
![Screenshot from 2024-10-22 00-01-49](https://github.com/user-attachments/assets/9c5ce120-0401-4dad-90a8-3dc5eff5fcb5)
![Screenshot from 2024-10-22 00-02-01](https://github.com/user-attachments/assets/60e09ffd-3ea3-4682-a674-8a1e774cc1f9)
![Screenshot from 2024-10-22 00-02-15](https://github.com/user-attachments/assets/62a51b4d-673f-4b71-adab-4dccfd5a58fa)
![Screenshot from 2024-10-22 00-02-30](https://github.com/user-attachments/assets/ea016dd8-1065-4c3d-902a-509ef04e1656)
![Screenshot from 2024-10-22 00-02-43](https://github.com/user-attachments/assets/ac29af21-00fa-43d0-b643-8a3997b190c9)
![Screenshot from 2024-10-22 00-05-40](https://github.com/user-attachments/assets/90aad655-3e51-4bd1-bc88-0711ab34d96e)
![Screenshot from 2024-10-22 00-06-58](https://github.com/user-attachments/assets/512d0873-eb98-4933-87ef-255a043894b9)
![Screenshot from 2024-10-22 00-09-33](https://github.com/user-attachments/assets/39883bde-5722-40d2-8603-54ef2f41ac7f)
![Screenshot from 2024-10-22 00-10-53](https://github.com/user-attachments/assets/ceb3ead8-2063-4a59-aea6-1f54d4e6d41f)
![Screenshot from 2024-10-22 00-13-41](https://github.com/user-attachments/assets/8dfe3eb8-7398-4ab0-9686-fa2f98f5ef94)
![Screenshot from 2024-10-22 00-14-22](https://github.com/user-attachments/assets/807de72d-4ba1-41f1-849f-d55a30959243)

#DAY-3

Optimization of Various Designs Design infers 2 input AND Gate:
![Screenshot from 2024-10-22 01-57-15](https://github.com/user-attachments/assets/b275f70c-6ccd-44cc-bebf-d0dffe7e8b64)
![Screenshot from 2024-10-22 01-58-01](https://github.com/user-attachments/assets/893413aa-bcac-4d7e-9e3d-bcb5f410a3fe)
![Screenshot from 2024-10-22 01-58-46](https://github.com/user-attachments/assets/1f4a8c7e-7faf-4772-be54-367300c73417)
![Screenshot from 2024-10-22 01-59-02](https://github.com/user-attachments/assets/8058d69c-a257-48eb-84b5-ecb1afad08c4)
![Screenshot from 2024-10-22 01-59-55](https://github.com/user-attachments/assets/bf405a29-ba25-4bc3-aa9d-55481f3ddaf0)
![Screenshot from 2024-10-22 02-01-39](https://github.com/user-attachments/assets/c651be3d-4d03-44f4-9761-1fe838e805cf)
![Screenshot from 2024-10-22 02-03-01](https://github.com/user-attachments/assets/de55705b-3242-47be-96b9-553c08d6f75e)
![Screenshot from 2024-10-22 02-03-23](https://github.com/user-attachments/assets/5331d499-7d2f-41d7-96d0-49431aa91b11)
![Screenshot from 2024-10-22 02-03-55](https://github.com/user-attachments/assets/2e737e41-0bc1-456f-8926-63e48ae0afca)
![Screenshot from 2024-10-22 02-04-50](https://github.com/user-attachments/assets/533f5fc6-fd01-4af6-b704-7f050c6baece)
![Screenshot from 2024-10-22 02-05-02](https://github.com/user-attachments/assets/904174c8-35e6-498f-97ef-c0aff28a2571)
![Screenshot from 2024-10-22 02-05-48](https://github.com/user-attachments/assets/ca7b98a4-dc33-4264-850c-967fe5cda251)
![Screenshot from 2024-10-22 02-06-03](https://github.com/user-attachments/assets/c51a430a-545c-45f7-8835-92e4556adb9b)
![Screenshot from 2024-10-22 02-06-28](https://github.com/user-attachments/assets/8962dd1e-336c-436b-950f-d911f3dd68b0)
![Screenshot from 2024-10-22 02-08-03](https://github.com/user-attachments/assets/d9d894fd-a583-476a-a5de-4a2f23b25e4d)
![Screenshot from 2024-10-22 02-08-17](https://github.com/user-attachments/assets/6a1ba608-0f38-41f9-81cf-c3d3a6dfa395)
![Screenshot from 2024-10-22 02-08-52](https://github.com/user-attachments/assets/387f3689-55be-499c-8194-99b910d48135)
![Screenshot from 2024-10-22 02-09-29](https://github.com/user-attachments/assets/2b6ce537-c2cd-4cf5-934c-893a67d376b1)
![Screenshot from 2024-10-22 02-13-44](https://github.com/user-attachments/assets/6a780e48-cae5-4dcb-964b-f5ce3a4ff4a9)
![Screenshot from 2024-10-22 02-16-36](https://github.com/user-attachments/assets/dbd510d2-03ff-4fec-bb8b-2af091df1269)
![Screenshot from 2024-10-22 02-17-55](https://github.com/user-attachments/assets/f57da4cc-ac24-4745-bff3-ee2e0f496218)
![Screenshot from 2024-10-22 02-18-09](https://github.com/user-attachments/assets/68fd7f23-fcab-4130-be1a-990ded54a5db)
![Screenshot from 2024-10-22 02-18-33](https://github.com/user-attachments/assets/f8358a6e-6adb-4f0a-a1d0-9bb7d49156f9)
![Screenshot from 2024-10-22 02-18-46](https://github.com/user-attachments/assets/a83cfac2-43ca-4240-bdef-138918eb13f8)
![Screenshot from 2024-10-22 02-18-58](https://github.com/user-attachments/assets/82b27987-1e0c-4ff6-a953-cc0c6f379549)
![Screenshot from 2024-10-22 02-19-12](https://github.com/user-attachments/assets/be4677c6-6ed0-45dc-a8f1-45fea0867f44)
![Screenshot from 2024-10-22 02-20-03](https://github.com/user-attachments/assets/542c8927-6fe9-4bf7-af7c-438e85558b74)
![Screenshot from 2024-10-22 02-20-23](https://github.com/user-attachments/assets/2c8661dd-9a0a-428b-8f1e-73772d8d179e)
![Screenshot from 2024-10-22 02-33-06](https://github.com/user-attachments/assets/c4328e59-f244-4065-a21c-134fed0562a7)
![Screenshot from 2024-10-22 02-33-39](https://github.com/user-attachments/assets/58fcb6cd-fd47-479a-bc97-2c58e90ea01b)
![Screenshot from 2024-10-22 02-34-56](https://github.com/user-attachments/assets/35606ea9-2005-4972-8d10-5f43b12c9eb8)
![Screenshot from 2024-10-22 02-35-46](https://github.com/user-attachments/assets/495be36b-ec41-4462-b20d-bc38a00803bc)
![Screenshot from 2024-10-22 02-37-11](https://github.com/user-attachments/assets/c2a266a8-9395-448d-a704-102a8a314f6e)
![Screenshot from 2024-10-22 02-38-03](https://github.com/user-attachments/assets/a2dd0d41-d04d-464a-aec9-70533dbf93ef)
![Screenshot from 2024-10-22 02-38-17](https://github.com/user-attachments/assets/c8a7360d-01ef-49e2-9fae-6050a733fefa)
![Screenshot from 2024-10-22 02-38-30](https://github.com/user-attachments/assets/53e6b6c0-1557-4924-a856-c19d5b32fc76)
![Screenshot from 2024-10-22 02-50-50](https://github.com/user-attachments/assets/69f2c836-0720-432f-abb1-af3f240b7390)
![Screenshot from 2024-10-22 02-51-33](https://github.com/user-attachments/assets/65caf579-be8f-4bbd-9810-b5b95367f0f3)
![Screenshot from 2024-10-22 02-52-18](https://github.com/user-attachments/assets/e73f8df6-2477-4019-a279-7c760577154d)
![Screenshot from 2024-10-22 02-52-51](https://github.com/user-attachments/assets/1dbf3ecb-78d3-4cee-878b-05ec1c0c9886)
![Screenshot from 2024-10-22 02-55-09](https://github.com/user-attachments/assets/fcb77ece-0c79-4a3b-ada8-bb1691895953)
![Screenshot from 2024-10-22 02-55-49](https://github.com/user-attachments/assets/abc81629-e32a-4b3c-8a6e-c661532ff43f)
![Screenshot from 2024-10-22 02-58-30](https://github.com/user-attachments/assets/8e1ab2d1-57dc-480e-a305-5a67f60253e1)
![Screenshot from 2024-10-22 02-59-14](https://github.com/user-attachments/assets/5b37e4b6-8e31-4edf-84b5-e62dfc63e01a)
![Screenshot from 2024-10-22 02-59-57](https://github.com/user-attachments/assets/0e3d9414-a4af-4936-8b0e-497ed6994e0e)
![Screenshot from 2024-10-22 03-00-37](https://github.com/user-attachments/assets/0650039f-6f77-4f8f-aaea-a6c5e8fc2a8c)
![Screenshot from 2024-10-22 03-00-50](https://github.com/user-attachments/assets/c45ddd9e-80b1-4dc4-af64-05f04120b40f)
![Screenshot from 2024-10-22 03-01-11](https://github.com/user-attachments/assets/66d9e054-00d3-4505-a26e-f98942538186)
![Screenshot from 2024-10-22 03-01-35](https://github.com/user-attachments/assets/c20129a4-c305-44f4-92d0-3aa2d6cdf9ce)
![Screenshot from 2024-10-22 03-02-58](https://github.com/user-attachments/assets/ff18cb8c-45b5-4f67-820c-e8b06ccd3277)
![Screenshot from 2024-10-22 03-03-46](https://github.com/user-attachments/assets/c20ef375-bfcf-41ff-97df-32303bbe5603)
![Screenshot from 2024-10-22 03-22-15](https://github.com/user-attachments/assets/36a007c8-c0bc-4614-b2b8-e97a5ff70a25)
![Screenshot from 2024-10-22 03-22-43](https://github.com/user-attachments/assets/26f228d8-80ff-41b3-b428-2fdd5b645b6e)
![Screenshot from 2024-10-22 03-23-25](https://github.com/user-attachments/assets/fee11293-a20f-48dd-92ba-5cb5c5b4e61e)

![Screenshot from 2024-10-22 03-23-38](https://github.com/user-attachments/assets/f5ad6708-4a0f-43ee-96e4-917df213d141)
![Screenshot from 2024-10-22 03-23-55](https://github.com/user-attachments/assets/25fe8f01-d694-4477-87aa-ad6c6d0796b5)
![Screenshot from 2024-10-22 03-24-28](https://github.com/user-attachments/assets/d6b227af-2635-44de-ae89-1d0d469fe99c)
![Screenshot from 2024-10-22 03-24-42](https://github.com/user-attachments/assets/92cec84b-b27f-4c97-ae26-69a0186273d3)
![Screenshot from 2024-10-22 03-25-18](https://github.com/user-attachments/assets/ade13d8d-f781-40de-9fbf-d14551da84a6)
![Screenshot from 2024-10-22 03-26-18](https://github.com/user-attachments/assets/246e87fa-2e61-4d5c-a6e9-fbb7ab8fcdb5)
![Screenshot from 2024-10-22 03-26-54](https://github.com/user-attachments/assets/c768e1ac-2627-4f17-b36d-4daab22be6a1)
![Screenshot from 2024-10-22 03-27-39](https://github.com/user-attachments/assets/7c1af861-56cf-4865-96ca-7f0d2d6d8eee)
![Screenshot from 2024-10-22 03-27-51](https://github.com/user-attachments/assets/555656f7-e191-4ce3-ad80-aa29243fa6b3)
![Screenshot from 2024-10-22 03-28-11](https://github.com/user-attachments/assets/b1e3dad9-fd46-4728-8cc6-cdedc9ed48fe)
![Screenshot from 2024-10-22 03-29-01](https://github.com/user-attachments/assets/6235c377-dc6c-42a8-b934-75ebd9624501)
![Screenshot from 2024-10-22 03-30-30](https://github.com/user-attachments/assets/b575c324-f6aa-4519-b662-42f5bc851c42)
![Screenshot from 2024-10-22 03-31-46](https://github.com/user-attachments/assets/fd5c1001-cd99-4448-a0ba-883d20c7ffd8)
![Screenshot from 2024-10-22 03-32-05](https://github.com/user-attachments/assets/2a8df7ca-96dd-4a08-9eb6-0e4f460c56f3)
![Screenshot from 2024-10-22 03-32-57](https://github.com/user-attachments/assets/3f7411a2-5dee-41cc-9aff-eab1094f83ed)
![Screenshot from 2024-10-22 03-33-09](https://github.com/user-attachments/assets/758a141b-94b2-4d93-bcab-b8b1dc6ca212)
![Screenshot from 2024-10-22 03-33-25](https://github.com/user-attachments/assets/9b90386f-4482-43f3-be94-d5563a74ae96)
![Screenshot from 2024-10-22 03-33-59](https://github.com/user-attachments/assets/9e0bd474-7f83-419f-9111-8120e1fad627)
![Screenshot from 2024-10-22 03-34-44](https://github.com/user-attachments/assets/b4f25853-77c6-4526-abb1-c01cd5fe1b96)
![Screenshot from 2024-10-22 03-36-55](https://github.com/user-attachments/assets/126717f7-4c72-4997-aec4-6b8eb38db9f1)
![image](https://github.com/user-attachments/assets/df00eb2c-0cf1-4567-8ac8-def2389564ab)






