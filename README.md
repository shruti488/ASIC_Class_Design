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


#DAY-4
Design of 2x1 MUX using Ternary Operator
![Screenshot from 2024-10-22 04-21-57](https://github.com/user-attachments/assets/abe47a26-fbcc-41a4-9858-98e653111c19)
![Screenshot from 2024-10-22 04-23-52](https://github.com/user-attachments/assets/16f6f8e8-925b-4a59-8729-b96a0baf1331)
![Screenshot from 2024-10-22 04-25-42](https://github.com/user-attachments/assets/0e8e6d07-4e33-443b-8207-2cfa76e1dc33)
![Screenshot from 2024-10-22 04-26-27](https://github.com/user-attachments/assets/59596022-897f-4b0b-ab6b-650339a4e1b6)
![Screenshot from 2024-10-22 04-26-42](https://github.com/user-attachments/assets/24718ce7-3487-4b06-8422-c5a4b55596e7)
![Screenshot from 2024-10-22 04-27-20](https://github.com/user-attachments/assets/2588b4bf-b378-4473-aa59-f4d11f27b8e1)
![Screenshot from 2024-10-22 04-27-36](https://github.com/user-attachments/assets/e1afe655-52d4-4015-8102-a50f21ba5cef)
![Screenshot from 2024-10-22 04-28-23](https://github.com/user-attachments/assets/28f2c1db-ee85-453e-96c6-cfcb3f7bb829)
![Screenshot from 2024-10-22 04-28-57](https://github.com/user-attachments/assets/5c4559dc-a5e1-4ce6-9ed2-9c8805d92899)
![Screenshot from 2024-10-22 04-29-16](https://github.com/user-attachments/assets/680fb212-6988-44be-a7d6-932d6f7c2798)
![Screenshot from 2024-10-22 04-31-12](https://github.com/user-attachments/assets/438288b4-a35e-40ca-bd47-971d38e17f0a)
![Screenshot from 2024-10-22 04-31-37](https://github.com/user-attachments/assets/c1fe4582-be65-4569-b128-3dfa6470ca0d)
![Screenshot from 2024-10-22 04-38-36](https://github.com/user-attachments/assets/acb2c94a-69ba-4e95-9c95-ff399a2b58b2)
![Screenshot from 2024-10-22 04-39-00](https://github.com/user-attachments/assets/309be8fa-10b5-418c-add8-aa7d0354ffff)
![Screenshot from 2024-10-22 04-40-51](https://github.com/user-attachments/assets/02b044e8-d489-4cd4-bb95-f4677fc7ee4c)
![Screenshot from 2024-10-22 04-41-28](https://github.com/user-attachments/assets/cda6a5b5-b505-4890-b5f8-2bf060dd81e4)
![Screenshot from 2024-10-22 04-42-25](https://github.com/user-attachments/assets/8299063b-a6f7-4e44-8783-d3cec3ea5f62)
![Screenshot from 2024-10-22 04-43-22](https://github.com/user-attachments/assets/bb98325f-095e-4913-a6ae-41985834899c)
![Screenshot from 2024-10-22 04-43-35](https://github.com/user-attachments/assets/9180a41c-3a89-4261-b11d-fb42cb8bc01c)
![Screenshot from 2024-10-22 04-44-24](https://github.com/user-attachments/assets/7d288025-0650-428c-acd2-8e1032a1b22a)
![Screenshot from 2024-10-22 04-44-37](https://github.com/user-attachments/assets/46705c59-23d8-427e-b614-b2bf0aa6f7ea)
![Screenshot from 2024-10-22 04-45-16](https://github.com/user-attachments/assets/92b40cd4-3802-4539-a492-c00cd8163b9d)
![Screenshot from 2024-10-22 04-45-46](https://github.com/user-attachments/assets/a8b8d049-eb00-401b-97d5-9d2409be16ff)
![Screenshot from 2024-10-22 04-46-19](https://github.com/user-attachments/assets/767a3221-ffce-48ff-863a-d74b44f3c59a)
![Screenshot from 2024-10-22 04-46-58](https://github.com/user-attachments/assets/ddabd4b2-894c-4c3d-8c42-9616ed47adaa)
![Screenshot from 2024-10-22 04-50-04](https://github.com/user-attachments/assets/3cd187e7-126a-436d-823e-b0ab77db0e68)
![Screenshot from 2024-10-22 04-51-29](https://github.com/user-attachments/assets/ae169422-a4f4-4084-b5fc-f5f1a12340c2)
![Screenshot from 2024-10-22 04-53-08](https://github.com/user-attachments/assets/f8dcd336-a2be-4a2d-8c75-831664c7935c)
![Screenshot from 2024-10-22 04-53-42](https://github.com/user-attachments/assets/d7a2fa7a-d1ce-476a-b21e-db56622d2fdb)
![Screenshot from 2024-10-22 04-55-27](https://github.com/user-attachments/assets/e478733e-ccf5-49be-83a3-fac56237ef72)
![Screenshot from 2024-10-22 04-56-07](https://github.com/user-attachments/assets/e41ee20c-9cca-4d1e-916d-19fff13feae2)
![Screenshot from 2024-10-22 04-56-19](https://github.com/user-attachments/assets/145aa5b2-0fe3-4c40-a2c9-4a76bff0e74e)
![Screenshot from 2024-10-22 04-57-14](https://github.com/user-attachments/assets/fb82f39f-94c6-4eb2-b06b-50cad4939ea9)
![Screenshot from 2024-10-22 04-58-00](https://github.com/user-attachments/assets/eb3ce164-02e8-45ea-a5f5-c61cfdb3dc47)
![Screenshot from 2024-10-22 04-58-31](https://github.com/user-attachments/assets/f0340171-4717-41ad-9c8a-23b60bb98009)
![Screenshot from 2024-10-22 04-59-12](https://github.com/user-attachments/assets/3e7b6f7a-15f6-4e27-980a-fc76992d7665)
![Screenshot from 2024-10-22 05-04-19](https://github.com/user-attachments/assets/787d9509-17de-4c76-b0ce-6bbb0ea19dbc)
![Screenshot from 2024-10-22 04-51-29](https://github.com/user-attachments/assets/ff0b4650-fa93-42b4-bec7-e95bf865b825)
![Screenshot from 2024-10-22 04-53-42](https://github.com/user-attachments/assets/346353c1-80a2-416c-81aa-fcbd951a6b26)
![Screenshot from 2024-10-22 05-05-18](https://github.com/user-attachments/assets/a00a25e3-8349-4c1e-825a-6ea00fd16d3b)


#ASSIGNMENT -9

Synthesis of RISCV verilog file and comparing the result

![Screenshot from 2024-10-24 20-18-38](https://github.com/user-attachments/assets/85797a97-ef95-4823-9313-ab33e346856e)
![Screenshot from 2024-10-24 20-22-09](https://github.com/user-attachments/assets/25fb39ca-8d97-4c72-851a-c92fe7c7bead)

![Screenshot from 2024-10-24 20-22-25](https://github.com/user-attachments/assets/23791189-8646-4dfb-a0c4-a4945e9f4399)
![Screenshot from 2024-10-24 20-22-49](https://github.com/user-attachments/assets/09e4cbd2-b698-45c3-a23c-5eb497bc7cd1)
![Screenshot from 2024-10-24 23-05-08](https://github.com/user-attachments/assets/6eb31567-1e82-44da-bab9-fa08025cadf2)
![Screenshot from 2024-10-24 23-05-25](https://github.com/user-attachments/assets/4e110783-93e0-4df1-955a-36826d4c325b)
![Screenshot from 2024-10-24 23-05-37](https://github.com/user-attachments/assets/c7efe29c-ffed-4af7-97c4-e38c52cbd960)
![Screenshot from 2024-10-24 23-05-49](https://github.com/user-attachments/assets/b3178296-c96f-4039-828f-f07f1b45accb)
![Screenshot from 2024-10-24 23-06-37](https://github.com/user-attachments/assets/8491df7a-037b-4f60-83d1-62353f8f8c69)
![Screenshot from 2024-10-24 23-06-48](https://github.com/user-attachments/assets/a2261303-172d-4ed9-99f6-35612c39b78d)
![Screenshot from 2024-10-24 23-07-01](https://github.com/user-attachments/assets/935026e7-3694-453a-b07b-f0709d30a95d)



#ASSIGNMENT -10

STATIC TIMING ANALYSIS
![Screenshot from 2024-10-29 09-13-38](https://github.com/user-attachments/assets/62390f40-c9e9-48b5-9a6a-6aa0aa996182)
![Screenshot from 2024-10-29 11-10-58](https://github.com/user-attachments/assets/ab821d68-9642-4a36-9d46-9bc0c9694368)
![Screenshot from 2024-10-29 11-14-46](https://github.com/user-attachments/assets/40279101-b0f5-4b48-8cff-6a2cf56ae304)
![Screenshot from 2024-10-29 09-19-50](https://github.com/user-attachments/assets/9730459c-d181-4cfa-9c78-5a0f7ba363b3)
![Screenshot from 2024-10-29 09-19-53](https://github.com/user-attachments/assets/81d37385-836b-49ee-a3c0-4269c8046285)


#ASSIGNMENT -11

In this task we are performing STA on the core netlist we generated, using other library files.
The sdc file is shown below : -
![Screenshot from 2024-11-05 21-53-53](https://github.com/user-attachments/assets/29acb70f-5912-4150-b92b-c2324c99fa55)

![Screenshot from 2024-11-05 21-55-24](https://github.com/user-attachments/assets/b9751ca0-6fbe-4af4-acf0-aabf9258e84d)
![Screenshot from 2024-11-05 21-56-39](https://github.com/user-attachments/assets/cda6cd51-3685-4e45-944d-b1a35c87c8f9)
![2](https://github.com/user-attachments/assets/334dea8c-1dd1-441c-8e96-d106556153c7)
![3](https://github.com/user-attachments/assets/eb9185f1-d61b-403a-86bd-6c1902f092b4)

#ASSIGNMENT -12
Advanced Physical Design using OpenLane using Sky130

DAY1:-  Inception of open-source EDA, OpenLane and Sky130 PDK

Synthesis in Openlane:
cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
run_synthesis
![Screenshot from 2024-11-15 06-46-23](https://github.com/user-attachments/assets/8c1d5b70-1eb9-4e0b-91e9-234a0e6c7b14)

![Screenshot from 2024-11-15 06-47-55](https://github.com/user-attachments/assets/ff73f98e-2288-45f9-9d13-67cbb0a944d7)
![Screenshot from 2024-11-15 06-48-52](https://github.com/user-attachments/assets/5a4e51d6-2d56-42c0-9aee-37426d686e80)

To view the yosys report:
cd ../..
cd reports/synthesis
gedit 1-yosys_4.stat.rpt
![Screenshot from 2024-11-15 06-52-06](https://github.com/user-attachments/assets/a7a1a8e2-5c32-4476-bb6c-159207794f49)
![Screenshot from 2024-11-15 06-52-35](https://github.com/user-attachments/assets/05f147cd-a9c9-44f3-ad45-613924223ebf)

Flop ratio = Number of D Flip flops = 1613  = 0.1084
             ______________________   _____
             Total Number of cells    14876

DAY2:-  Good floorplan vs bad floorplan and introduction to library cells

Floorplaning using OpenLANE:

cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
run_synthesis
run_floorplan
![2a](https://github.com/user-attachments/assets/e8139a44-0080-4dc2-9bb2-aaae925c17dc)
![2b](https://github.com/user-attachments/assets/65f776b0-01b8-4b84-b128-cb6e578e3dc1)
![2c](https://github.com/user-attachments/assets/e8176f9a-f611-44f4-9eb0-c72cbfdac154)

Calculate the die area in microns from the values in floorplan def.

![2d](https://github.com/user-attachments/assets/7709009a-e09d-42c6-a2cf-1783673355e8)
![2e](https://github.com/user-attachments/assets/87d3b638-1c3f-4a25-88ca-b1ffa81d17ad)

According to floorplan definition:

1000 Unit Distance = 1 Micron

Die width in unit distance = 660685−0 = 660685

Die height in unit distance = 671405−0 = 671405

Distance in microns = Value in Unit Distance/1000

​Die width in microns = 660685/1000 = 660.685 Microns

Die height in microns = 671405/1000 = 671.405 Microns

Area of die in microns = 660.685 × 671.405 = 443587.212425 Square Microns

To view the floorplan in magic. Open a new terminal and run the below commands:

cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/09-11_07-10/results/floorplan/
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &

![2f](https://github.com/user-attachments/assets/53034697-fb51-4bbf-b405-dfb6da84053c)
![2g](https://github.com/user-attachments/assets/3b63a3cf-9b53-42f1-a502-f4e918fe0390)

Command to run placement:

run_placement

![2h](https://github.com/user-attachments/assets/46d4f51a-f9ec-47e4-9cc6-5da947291946)

To view the placement in magic:

cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/17-03_12-06/results/placement/
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

![2i](https://github.com/user-attachments/assets/9972ddf7-768f-4963-8244-67041a28ea7b)

# Exit from OpenLANE flow
exit

# Exit from OpenLANE flow docker sub-system
exit

DAY -3
 Design library cell using Magic Layout and ngspice characterization

 Creating a SPICE Deck for a CMOS Inverter Simulation

    Netlist Creation: Define the component connections (netlist) for a CMOS inverter circuit. Ensure each node is labeled appropriately for easy identification in the SPICE simulation. Typical nodes include input, output, ground, and supply nodes.
    Device Sizing: Specify the Width-to-Length (W/L) ratios for both the PMOS and NMOS transistors.For proper operation, the PMOS width should be larger than the NMOS width, usually 2x to 3x, to balance the drive strength
    Voltage Levels: Set gate and supply voltages, often in multiples of the transistor length.
    Node Naming: Assign node names to each connection point around the components to clearly identify each element in the SPICE netlist (e.g., VDD, GND, IN, OUT). This helps SPICE recognize each component and simulate the circuit effectively.

#Clone custom inverter standard cell design from github repository

# Change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

# Clone the repository with custom inverter design
git clone https://github.com/nickson-jose/vsdstdcelldesign

# Change into repository directory
cd vsdstdcelldesign

# Copy magic tech file to the repo directory for easy access
cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech .

# Check contents whether everything is present
ls

# Command to open custom inverter layout in magic
magic -T sky130A.tech sky130_inv.mag &
![3a](https://github.com/user-attachments/assets/f8f8d5cd-7bf7-4586-bf3e-e5f5e4590ad1)
![3b](https://github.com/user-attachments/assets/c35b4c69-cb3a-47fa-b879-473fd6ce89e2)

 Spice extraction of inverter in magic.

 ![3c](https://github.com/user-attachments/assets/47a1a158-4cee-4487-9919-5cc1d48143b6)
![3d](https://github.com/user-attachments/assets/9cd92007-f5be-43c2-9d45-677d2ac45ac1)
![3](https://github.com/user-attachments/assets/e7d72f3d-3b9c-4a74-b35b-e645113307ff)

Editing the spice model file for analysis through simulation.

![3A](https://github.com/user-attachments/assets/9f59cd1d-e7f6-496d-9073-9dd9a2081487)

Post-layout ngspice simulations.

# Command to directly load spice file for simulation to ngspice
ngspice sky130_inv.spice

# Now that we have entered ngspice with the simulation spice file loaded we just have to load the plot
plot y vs time a
![3e](https://github.com/user-attachments/assets/7748048d-b34e-49f7-be8f-de8c815a40c7)
![3h](https://github.com/user-attachments/assets/e79540d0-b70c-418a-92db-ee71db34a844)

Magic Tool options and DRC Rules:

cd
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
tar xfz drc_tests.tgz
cd drc_tests
ls -al
gvim .magicrc
magic -d XR &

![3i](https://github.com/user-attachments/assets/60803f0a-1a35-4ea8-98c8-edbe42657226)
![3j](https://github.com/user-attachments/assets/236b4353-d8d2-43d7-8ec3-6ef671fbb923)

First load the poly file by load poly.mag on tkcon window.

Run the commands in tkcon window

tech load sky130A.tech
drc check
drc why
![3m](https://github.com/user-attachments/assets/84f374f4-be09-4fe1-8f6b-9886d1caeafe)
![g](https://github.com/user-attachments/assets/d39a47cd-7676-423c-8b8a-12adc45164e3)


#DAY -4
Pre-layout timing analysis and importance of good clock tree

Commands to extract tracks.info file:

cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
cd ../../pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd/
less tracks.info

![4a](https://github.com/user-attachments/assets/58c58fbd-2c56-49f6-82c2-6073e9b34e29)

grid 0.46um 0.34um 0.23um 0.17um
![4b](https://github.com/user-attachments/assets/bc39ee78-5fcf-4e51-96d8-32c6bb649a98)

Now, save it by giving a custom name

save sky130_shr_inv.mag
Now, open it by using the following commands:

magic -T sky130A.tech sky130_ashr_inv.mag &

![4c](https://github.com/user-attachments/assets/60c49a0d-6b92-46c2-890e-3cd5e3051db7)

Now, type the following command in tkcon window:

lef write

![4d](https://github.com/user-attachments/assets/ddfae86a-b4ec-45d7-8796-8993a5a3874f)

![4e](https://github.com/user-attachments/assets/ca5c5ed9-3bc7-410b-918e-ee548401af5b)

Modify config.tcl:

# Design
set ::env(DESIGN_NAME) "picorv32a"

set ::env(VERILOG_FILES) "./designs/picorv32a/src/picorv32a.v"
set ::env(SDC_FILES) "./designs/picorv32a/src/picorv32a.sdc"


set ::env(CLOCK_PERIOD) "5.000"
set ::env(CLOCK_PORT) "clk"

set ::env(CLOCK_NET) $::env(CLOCK_PORT) 


set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib "
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib "
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]   ## this is the new line added to the existing config.tcl file

set filename $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/$::env(PDK)_$::env(STD_CELL_LIBRARY)_config.tcl
if { [file exists $filename] == 1 } {
  source $filename
}

Now, run openlane flow synthesis:
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
run_synthesis
![4e](https://github.com/user-attachments/assets/48986155-bcda-44c8-9dc9-8b686cdbac15)
![4f](https://github.com/user-attachments/assets/6ffdeb75-fe67-4fd2-b7ad-bc7af8d77fb4)
![4gbefore](https://github.com/user-attachments/assets/37201fe6-1f66-4e99-9109-9013202d1fe6)
![4g](https://github.com/user-attachments/assets/0231f2d4-a6b3-49d6-9bc6-336e5ee7f3fa)

Delay Tables

Delay plays a crucial role in cell timing, impacted by input transition and output load. Cells of the same type can have different delays depending on wire length due to resistance and capacitance variations. To manage this, "delay tables" are created, using 2D arrays with input slew and load capacitance for each buffer size as timing models. Algorithms compute buffer delays from these tables, interpolating where exact data isn’t available to estimate delays accurately, preserving signal integrity across varying load conditions

./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag 24-03_10-03 -overwrite
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
echo $::env(SYNTH_STRATEGY)
set ::env(SYNTH_STRATEGY) "DELAY 3"
echo $::env(SYNTH_BUFFERING
echo $::env(SYNTH_SIZING)
set ::env(SYNTH_SIZING) 1
echo $::env(SYNTH_DRIVING_CELL)
run_synthesis
![4h](https://github.com/user-attachments/assets/266cfa95-2311-4132-99da-2a2a4c140d60)
![4i](https://github.com/user-attachments/assets/edf89740-e5a3-41ad-b498-25739d6385a6)
![4j](https://github.com/user-attachments/assets/7671dc54-16c5-4f69-8dab-56729aa67944)
![4k](https://github.com/user-attachments/assets/dd556c69-f7cd-4f67-b29b-6a89f4d3ea79)
![4l](https://github.com/user-attachments/assets/4d788729-db42-4e2a-912f-a6fb2cbde9b6)

Now, run floorplan

run_floorplan
![4m](https://github.com/user-attachments/assets/05d0c077-19b5-425f-be0a-2bd7e1a7481c)
![4n](https://github.com/user-attachments/assets/7eeaad08-bdf7-46cc-a78d-68706117b9a2)
![4p](https://github.com/user-attachments/assets/f6a08a5f-a934-463b-afa2-7a551b67ebf9)

Now, open a new terminal and run the below commands to load placement def in magic

cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/24-03_10-03/results/placement/
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

![4q](https://github.com/user-attachments/assets/2f4e367a-0f9b-4cbe-b3d6-23a8345f65ec)
![4r](https://github.com/user-attachments/assets/269eaaed-96ab-4170-8085-31a032046b5f)

Timing analysis with ideal clocks using openSTA
Pre-layout STA will include effects of clock buffers and net-delay due to RC parasitics (wire delay will be derived from PDK library wire model).

Commands to invoke the OpenLANE flow include new lef and perform synthesis:

cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
package require openlane 0.9set
prep -design picorv32a
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
set ::env(SYNTH_SIZING) 1
run_synthesis

Go, to Desktop/work/tools/openlane_working_dir/openlane and create a file pre_sta.conf. The contents of the file are:

set_cmd_units -time ns -capacitance pF -current mA -voltage V -resistance kOhm -distance um
read_liberty -max /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read_liberty -min /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
read_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/24-03_10-03/results/synthesis/picorv32a.synthesis.v
link_design picorv32a
read_sdc /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/my_base.sdc
report_checks -path_delay min_max -fields {slew trans net cap input_pin}
report_tns
report_wns

Contents of my_base.sdc:

set ::env(CLOCK_PORT) clk
set ::env(CLOCK_PERIOD) 12.000
set ::env(SYNTH_DRIVING_CELL) sky130_fd_sc_hd__inv_8
set ::env(SYNTH_DRIVING_CELL_PIN) Y
set ::env(SYNTH_CAP_LOAD) 17.65
create_clock [get_ports $::env(CLOCK_PORT)]  -name $::env(CLOCK_PORT)  -period $::env(CLOCK_PERIOD)
set IO_PCT  0.2
set input_delay_value [expr $::env(CLOCK_PERIOD) * $IO_PCT]
set output_delay_value [expr $::env(CLOCK_PERIOD) * $IO_PCT]
puts "\[INFO\]: Setting output delay to: $output_delay_value"
puts "\[INFO\]: Setting input delay to: $input_delay_value"


set clk_indx [lsearch [all_inputs] [get_port $::env(CLOCK_PORT)]]
#set rst_indx [lsearch [all_inputs] [get_port resetn]]
set all_inputs_wo_clk [lreplace [all_inputs] $clk_indx $clk_indx]
#set all_inputs_wo_clk_rst [lreplace $all_inputs_wo_clk $rst_indx $rst_indx]
set all_inputs_wo_clk_rst $all_inputs_wo_clk


# correct resetn
set_input_delay $input_delay_value  -clock [get_clocks $::env(CLOCK_PORT)] $all_inputs_wo_clk_rst
#set_input_delay 0.0 -clock [get_clocks $::env(CLOCK_PORT)] {resetn}
set_output_delay $output_delay_value  -clock [get_clocks $::env(CLOCK_PORT)] [all_outputs]

# TODO set this as parameter
set_driving_cell -lib_cell $::env(SYNTH_DRIVING_CELL) -pin $::env(SYNTH_DRIVING_CELL_PIN) [all_inputs]
set cap_load [expr $::env(SYNTH_CAP_LOAD) / 1000.0]
puts "\[INFO\]: Setting load to: $cap_load"
set_load  $cap_load [all_outputs]

Commands to run STA:

cd Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
![4s](https://github.com/user-attachments/assets/ae67b667-9df5-45ab-8a17-89b03e0bf72f)
![4t](https://github.com/user-attachments/assets/c62a402a-f8a4-4009-9bd4-a8eade312dd3)
![4u](https://github.com/user-attachments/assets/ad890ba4-f4af-43e8-88c9-3718cd03f497)
![4v](https://github.com/user-attachments/assets/734874d7-66dc-4406-aa17-34a941f00833)

We now try to optimise synthesis.

Go to new terminal and run the following commands:

cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
prep -design picorv32a -tag 25-03_18-52 -overwrite
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
set ::env(SYNTH_SIZING) 1
set ::env(SYNTH_MAX_FANOUT) 4
echo $::env(SYNTH_DRIVING_CELL)
run_synthesis

Commands to run STA:

cd Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
![4x](https://github.com/user-attachments/assets/29638216-af85-49e2-9ca7-8ea9204fdaa3)
![4y](https://github.com/user-attachments/assets/a7e6d1f3-be23-4f58-bdff-e92847f26a58)

Basic timing ECO

NOR gate of drive strength 2 is driving 5 fanouts
![4z](https://github.com/user-attachments/assets/964e42f0-7669-4443-b43d-4f1fa8749b32)
![40](https://github.com/user-attachments/assets/f178f5d8-84d5-400b-b28d-f131607caebe)
![41](https://github.com/user-attachments/assets/7c4cdb4f-fcd2-4d19-928f-2d4884b53b2d)
![42](https://github.com/user-attachments/assets/7bb07593-9423-4c70-8b54-b3823bc93cb1)
![43](https://github.com/user-attachments/assets/da5fdd9f-3a5e-4a60-b3a1-f063cdc81d50)
![44](https://github.com/user-attachments/assets/c91c6506-778c-4f48-a340-10293e8627a3)
![45nor](https://github.com/user-attachments/assets/9d4ce58a-710a-4579-bee9-853269971a69)
![47](https://github.com/user-attachments/assets/92b7b369-211e-4497-8674-1b6e9de246ae)
![48](https://github.com/user-attachments/assets/12cba57a-ecb4-4a34-8b8d-d8484ae6deb1)

Clock tree synthesis TritonCTS and signal integrity

Clock Tree Synthesis (CTS) techniques vary based on design needs:

    Balanced Tree CTS: Uses a balanced binary-like tree for equal path lengths, minimizing clock skew but with moderate power efficiency.

    H-tree CTS: Employs an "H"-shaped structure, good for large areas and power efficiency.

    Run the following commands:

cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/
ls
cp picorv32a.synthesis.v picorv32a.synthesis_old.v
ls

Commands to write verilog:

write_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/picorv32a.synthesis.v
exit

Now, run the following commands:

cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
prep -design picorv32a -tag 25-03_18-52 -overwrite
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
set ::env(SYNTH_STRATEGY) "DELAY 3"
set ::env(SYNTH_SIZING) 1
run_synthesis
init_floorplan
place_io
tap_decap_or
run_placement
run_cts

![49](https://github.com/user-attachments/assets/3a866525-148d-416f-8c29-a734921448b9)
![410](https://github.com/user-attachments/assets/e4b2e59b-604b-4f26-895b-33e3b88720b9)
![411](https://github.com/user-attachments/assets/0ce6716c-4ae2-40ce-9692-8fe5ccb822e1)
![412](https://github.com/user-attachments/assets/391dde8e-8564-4993-a7c0-ec6e78e7e470)
![413](https://github.com/user-attachments/assets/f5582b4e-be2b-4965-a707-aee805164fdb)
![414](https://github.com/user-attachments/assets/204ee119-be1c-4bdb-90b4-129cc3cf1da3)
![415](https://github.com/user-attachments/assets/dd152288-2514-4677-9624-009c2a563b4d)
![416](https://github.com/user-attachments/assets/472ca6e4-8909-4b79-b952-930baf3f5b47)
![417](https://github.com/user-attachments/assets/50ef7676-6a33-47f6-b5b5-5ad2f3888d57)

#ASSIGNMENT -13

OpenRoad Physical Design

INTRODUCTION

Bombe: The Bombe was an electro-mechanical machine designed during World War II to decrypt German Enigma-encrypted messages. It was refined and built by Alan Turing and Gordon Welchman at Bletchley Park, UK. The Bombe systematically tested possible rotor settings of the Enigma machine by exploiting known plaintext patterns. Its logical operations helped narrow down the vast number of possible keys, significantly accelerating the decryption process. The Bombe played a critical role in the Allied war effort.

ENIAC (Electronic Numerical Integrator and Computer): It was developed during World War II by John Presper Eckert and John Mauchly at the University of Pennsylvania, was the first general-purpose, fully electronic digital computer. Completed in 1945, it was designed to compute artillery firing tables for the U.S. Army. ENIAC used vacuum tubes instead of mechanical or electromechanical components. However, it lacked a stored-program capability, requiring manual reconfiguration for each new task. ENIAC demonstrated the immense potential of electronic computing for large-scale numerical problems.

EDVAC (Electronic Discrete Variable Automatic Computer): EDVAC, also developed by Eckert and Mauchly with conceptual input from John von Neumann, was one of the first computers to implement the stored-program concept. Completed in 1949, EDVAC represented a significant improvement over ENIAC by using binary representation instead of decimal and storing both data and instructions in memory. This innovation simplified programming and laid the groundwork for the modern von Neumann architecture.

50 Years of Microprocessor Trend Data:
![11](https://github.com/user-attachments/assets/a0a0acdb-7c18-426e-910b-7ea35a31838a)

Transistors (Orange Triangles): The number of transistors on a microprocessor chip (in thousands) has increased exponentially, following Moore's Law, which predicts a doubling approximately every two years. This growth enabled more complex and capable processors, reaching the range of billions of transistors by the 2020s.
Single-Thread Performance (Blue Circles): It is measured using SpecINT. It indicates the computational ability of a single processor core. Performance grew steadily due to improvements in architecture, instruction-level parallelism, and clock speeds, but the growth rate slowed post-2005 due to physical limitations like power and heat.
Frequency (Green Diamonds): Processor clock speed (in MHz) rose steadily until the early 2000s but then stagnated as increasing clock speeds became inefficient due to heat dissipation issues.
Typical Power (Red Triangles): Power consumption increased with transistor density and frequency, becoming a critical design challenge around the mid-2000s.
Number of Logical Cores (Black Dots): The transition to multi-core processors gained momentum in the mid-2000s as a response to the stagnation in single-thread performance. By increasing the number of cores, processors enabled more efficient parallel processing, leading to significant improvements in overall performance

Key Milestones

iPhone Release (~2007): Signals the emergence of mobile computing, where power efficiency became as crucial as performance. This catalyzed innovations in low-power processor designs.
Datacenter-Scale Computing (Post-2010): Marks the rise of cloud computing and large-scale data centers, where energy efficiency, scalability, and parallelism became central concerns.

![image](https://github.com/user-attachments/assets/a0f49309-b2a0-4c50-b749-01652a09969b)

Key Performance Levels

Gigascale (10⁹ FLOPS): The starting point in 1984, marking the capability of early supercomputers.
Terascale (10¹² FLOPS): Achieved around 1997, a significant milestone where systems like Jaguar (Cray XT5) delivered teraflop performance with power consumption of 7 MW.
Petascale (10¹⁵ FLOPS): Achieved in 2008 with systems like Titan (Cray XK6) at 27 petaflops, consuming 9 MW. This milestone represents the era of petascale high-performance computing (HPC).
Exascale (10¹⁸ FLOPS): Reached by systems like Frontier (Cray Shasta) in 2021, delivering 1.5 exaflops using 4 AMD GPUs and 1 AMD CPU, consuming 29 MW of power. Exascale computing enables highly detailed simulations and large-scale AI workloads.

Zettascale (10²¹ FLOPS): Projected to be achieved by around 2035. At this scale, systems will handle unprecedented computational workloads, such as advanced climate modeling, AI, and large-scale simulations. Power consumption is estimated to range between 50-100 MW for a single zettascale machine.

CMOS Evolution and Next-Gen Candidates

![image](https://github.com/user-attachments/assets/b76d071d-f3e4-4052-9aea-641b70b5bea2)

This diagram illustrates the evolving landscape of CMOS (Complementary Metal-Oxide-Semiconductor) technology and highlights emerging materials, structures, and processes being explored for next-generation semiconductor devices. These innovations aim to address the challenges of scaling CMOS technology down to the 1nm node and beyond.

Channel Material

Current Trends:

Silicon (Si) is the primary material used for the channel in traditional CMOS transistors, with strained SiGe (Silicon-Germanium) being used in some high-performance applications to enhance carrier mobility.

Future Materials:

2D materials such as MoS₂ (Molybdenum Disulfide) are being explored due to their potential for better electrical characteristics at smaller scales.
Germanium (Ge) is gaining interest as it offers higher electron mobility, which could significantly boost transistor performance at small nodes.
Patterning

Current Techniques:
Deep Ultraviolet (DUV) lithography is the most commonly used technique for defining transistor features, with ArF (Argon Fluoride) and KrF (Krypton Fluoride) lasers operating at different wavelengths.
Next-Gen:

Extreme Ultraviolet (EUV) lithography is expected to be a key technology for sub-7nm nodes. High-NA (Numerical Aperture) EUV will further improve the resolution for even smaller transistor nodes, pushing the boundaries of Moore's Law.
Gate Stack Material

Current Materials:

High-K metal gates (HKMG) are used in the gate stack of modern FETs to reduce gate leakage current and improve switching performance.

Next-Gen Candidates:
NC-FET (Negative Capacitance FET): This is a promising transistor design that leverages ferroelectric materials to reduce power consumption by enabling lower voltage operation.
TFET (Tunnel FET): TFETs use quantum tunneling to switch on and off, offering a significant reduction in power consumption compared to conventional FETs, especially for low-power applications.
Interconnection Material

Current Materials:

Copper (Cu) is the primary material used for interconnects due to its low resistivity, which helps in minimizing power loss and delays in transistor connections.
Next-Gen Materials:

Ruthenium (Ru) and Compound metals are being investigated for their potential to reduce resistance and improve performance in ultra-small transistors.
Topological semi-metals may offer unique properties, such as lower resistivity and increased performance at the atomic scale.

Device Structure

Current Architectures:

FinFET and planar transistors are used to maintain performance at smaller nodes. FinFETs, in particular, help improve control over short-channel effects by using a 3D structure.
Next-Gen Architectures:

3DS-FET (3D Stacked FET): These are three-dimensional transistors where multiple layers of devices are stacked vertically, reducing footprint and improving performance.
MBC-FET (Multi-Bridge Channel FET): This structure aims to enhance drive current by creating multiple channels within the same device.
VFET (Vertical FET): VFETs utilize vertical channels to improve density and reduce power consumption.

Design Co-Optimization

DTCO (Design-Technology Co-Optimization):

DTCO focuses on integrating new design techniques with advanced process technologies to maximize chip performance, often involving backside interconnects (BSI), where interconnections are made at the back of the wafer for improved signal integrity and reduced latency.
STCO (System-Technology Co-Optimization):

This approach involves optimizing both the system architecture and the underlying technology. One example is the use of chiplets, which allow for modular, customized designs by integrating multiple smaller chips into one package, offering flexibility and reducing the complexity of scaling single-chip designs.

FinFETs

![image](https://github.com/user-attachments/assets/f22249ad-12a2-4c2b-8f7c-06be9a391845)

This diagram illustrates the evolution of transistor technology from planar to more advanced architectures like FinFET and Gate-All-Around (GAA):

Planar Transistor (Traditional):

Early transistor design with a flat channel and gate structure.
The gate controls the channel from one side only, leading to limited performance as scaling continues.

FinFET (2011):

The channel is shaped like a vertical fin, allowing the gate to wrap around three sides of the channel.
Provides better control over the channel, reducing leakage and improving performance at smaller sizes.
Gate-All-Around (GAA) Transistor (2025?):

The gate completely surrounds the channel, typically implemented using stacked nanosheets or nanowires.
Offers even better control over the channel compared to FinFET, allowing higher performance and efficiency with continued scaling.

Each step improves drive current capability and enhances control over the transistor's on/off states, critical for power efficiency and miniaturization in modern electronics.

Why FinFETs and Gate-All-Around Transistors?

![image](https://github.com/user-attachments/assets/645223ff-241a-4003-a2c0-2800f80ee69d)

This diagram explains the advantages of FinFETs and Gate-All-Around (GAA) transistors compared to traditional planar structures:

Planar Transistors:
Challenges:
Sub-channel leakage occurs where current leaks underneath the gate.
Results in reduced efficiency.
Increases power consumption.
FinFET Transistors:

The gate wraps around the channel (fin) on three sides, providing better control over the channel.

This diagram explains the advantages of FinFETs and Gate-All-Around (GAA) transistors compared to traditional planar structures:

Planar Transistors:
Challenges:
Sub-channel leakage occurs where current leaks underneath the gate.
Results in reduced efficiency.
Increases power consumption.
FinFET Transistors:

The gate wraps around the channel (fin) on three sides, providing better control over the channel.
Advantages:
Improves short-channel performance by reducing drain capacitance and enhancing gate capacitance.
Improves scaling efficiency as indicated by the formula (S \propto (1 + C_d / C_{ox})).
Provides reduced sub-threshold slope and better performance at smaller scales.
Graph Comparison:

Illustrates the performance advantages of FinFETs and GAA over planar transistors.
Shows better efficiency and reduced sub-threshold slope as dimensions shrink.

![image](https://github.com/user-attachments/assets/4848cf24-46b4-46a9-a96e-6e7bf7c97d0e)

Reduced Leakage: Tri-Gate transistors exhibit significantly lower leakage current compared to planar transistors at the same gate voltage. Lower leakage results in both reduced off-current at the same on-current and lower power dissipation.

Higher Drive Current: Tri-Gate transistors provide higher drive current compared to planar transistors at the same off-current. This results in improved circuit performance and greater efficiency in modern electronic applications.

FEOL Innovations:
FEOL refers to the initial stages of semiconductor manufacturing where the active devices (e.g., transistors) are built on the silicon wafer. It involves creating components such as transistors, capacitors, and isolation structures before metal interconnects are added. FEOL Innovations help drive Moore's Law forward by enabling smaller, more efficient, and more powerful transistors.

CMOS Technology Inflection Points

![image](https://github.com/user-attachments/assets/169a4c34-5bb4-49d6-8574-37e42bba7b20)

Dennard Scaling:

States that power density remains constant as transistors shrink.
Initially allowed voltage scaling with smaller gate lengths, shown in the bottom-left graph.
Technology Nodes and Innovations:

~1 µm ("End of Scaling"): Start of CMOS miniaturization.
180 nm (Voltage Scaling): Start of drive voltage reduction.
130 nm (Cu BEOL): Introduction of copper interconnects for better conductivity.
90 nm (Uniaxial Strained Si NMOS): Strained silicon enhances electron mobility.
65 nm (eSiGe CVD ULK): Embedded SiGe improves PMOS performance.
45 nm (HK-first MG-last): High-k dielectrics and metal gates reduce leakage and improve gate control.
32 nm (HKMG with Raised S/D NMOS): Advanced HKMG implementation and raised source/drain regions.

SEM Images

Left Image: Shows the cross-sectional view of a transistor structure with High-k materials and embedded SiGe (Silicon-Germanium).It has high-k dielectric and metal gates are used to improve performance. SiGe regions enhance PMOS performance by applying strain to the silicon channel.

Right Image: Demonstrates the raised source/drain (S/D) regions and gate channel in PMOS transistors at smaller nodes.

Drive Voltage Scaling Graph (Bottom-left): The graph shows the relationship between gate length (x-axis, logarithmic scale) and drive voltage (y-axis, logarithmic scale). The Ideal scaling behavior indicates that the voltage decreases linearly with shrinking gate length. Red and green markers show practical trends for low-power and high-performance devices, which deviate from ideal scaling due to challenges like leakage currents and increased power density.

![image](https://github.com/user-attachments/assets/2e79f03e-dd78-4442-8604-01835d0d2555)

Key Technology Nodes and Innovations

22 nm:

Introduction of FinFET (Tri-Gate) transistors, which reduce leakage and improve gate control.
Use of self-aligned contacts (SAC) and copper interconnects (Co+Cu BEOL).
14 nm:

Transition to unidirectional metal routing for better density.
Implementation of SADP (Self-Aligned Double Patterning) and SDB (Single Diffusion Break) for precise layout.

14 nm:

Transition to unidirectional metal routing for better density.
Implementation of SADP (Self-Aligned Double Patterning) and SDB (Single Diffusion Break) for precise layout.
10 nm:

Adoption of advanced patterning techniques such as:
SA-SDB (Self-Aligned SDB)
LELELE (Litho-Etch-Litho-Etch-Litho-Etch)
SAQP (Self-Aligned Quadruple Patterning) for tighter geometries.
7 nm:

Introduction of Extreme Ultraviolet Lithography (EUV) to simplify the patterning process and reduce overlay errors.
5 nm:

Integration of SiGe (Silicon-Germanium) channels for PMOS to enhance hole mobility.
Use of EUV SA-LELE (Self-Aligned Litho-Etch-Litho-Etch).

3 nm / 2 nm / 1.4 nm:

Transition to Gate-All-Around (GAA) nanosheet transistors for improved electrostatic control.
GAA stacks nanosheets or nanowires horizontally to maximize current drive.
Sub-1 nm:

Development of CFET (Complementary FET), which vertically stacks NMOS over PMOS to save area.
Use of 2D materials, such as MoS₂, for atomic-scale channel thickness in 2D FETs.

![image](https://github.com/user-attachments/assets/11a878fa-6d1f-44ea-920e-fb66ae432f62)

The image illustrates how Samsung has scaled down the size of transistors in their successive generations of nodes (10nm, 8nm, 7nm, and 5nm) using a technique called Fin Depopulation. In FinFET transistors, the "fin" is the vertical channel that carries the current. Fin Depopulation involves reducing the number of fins per transistor while keeping the fin width constant. This allows for smaller transistors without compromising performance.

10nm (HD): The transistor has a fin height of 420nm and uses 10 fins.
8nm (UHD): The fin height is reduced to 378nm, and the number of fins is decreased to 9.
7nm (HD): The fin height remains at 27nm, but the number of fins is further reduced to 8.
5nm (UHD): The fin height is maintained at 27nm, and the number of fins is decreased to 7.
![image](https://github.com/user-attachments/assets/aaf97aba-74e7-48ae-b662-bee664bbc089)

Double Diffusion Break (DDB): Double Diffusion Break (DDB) involves creating a gap between the source and drain regions of a transistor. This gap is filled with an insulating material, which reduces the effective width of the transistor. By doing so, DDB enables the design of smaller cell sizes, allowing for higher transistor density and improved scalability. A cross-sectional view of a transistor with DDB highlights the insulating gap between the source and drain regions.

Single Diffusion Break (SDB): Single Diffusion Break (SDB) is similar to DDB but less aggressive. It involves introducing a gap on only one side of the transistor. This approach provides a balanced trade-off between size reduction and maintaining transistor performance. A cross-section of a transistor with SDB highlights the gap on one side, showcasing its simplicity compared to DDB.

Contact Over Field Gate (COFG): Contact Over Field Gate (COFG) places the gate contact directly over the field oxide region of a transistor. This design reduces lateral spacing between adjacent transistors, enabling smaller cell sizes without significant performance loss. A cross-sectional representation of a transistor with COFG illustrates the positioning of the gate contact over the field oxide.

Contact Over Active Gate (COAG): Contact Over Active Gate (COAG) is a more aggressive technique than COFG. Here, the gate contact is placed directly over the active gate region of the transistor. This approach enables even smaller cell sizes and higher transistor density, which are critical for advanced semiconductor nodes. A cross-sectional image of a transistor with COAG highlights the gate contact placement over the active gate.

Back-Side Power Delivery Network (BS-PDN): The Back-Side Power Delivery Network (BS-PDN) is an innovative approach where power supply rails are routed on the backside of the chip. This method reduces the height of the standard cell, creating space for more transistors and improving overall transistor density. Additionally, it enhances power delivery efficiency and reduces resistance, which is crucial for high-performance applications. A schematic of a standard cell with BS-PDN illustrates the positioning of power rails on the backside of the chip.

![image](https://github.com/user-attachments/assets/5586ddf4-320a-4fab-8fcf-7a9cbf7dfa2e)

Planar Technology: In early planar technology nodes (100nm and above), the Vt variability is significantly high, around 130mV. This is due to various factors like process variations, temperature fluctuations, and line-edge roughness.

FinFET Technology: With the advent of FinFET technology (around 22nm), the Vt variability reduces significantly to around 14mV. This improvement is attributed to the better control over the channel length and width in FinFETs compared to planar transistors.

NW Technology (Nanowire): In the latest nanowire technology (14nm and below), the Vt variability is even lower, around 7mV. This further reduction is due to the precise control over the nanowire dimensions and the reduced impact of process variations.

Planar MOSFETs
Planar MOSFETs, the traditional architecture, have a simple structure where the gate sits above the channel. In this design, the contact width ((W_C)) and gate width ((W_G)) are nearly equal, resulting in a ratio of (W_C / W_G \approx 1). This leads to a low parasitic resistance, with (R_{EXT}) being much smaller than (R_{ch}) ((R_{EXT} / R_{ch} < 1)). As a result, planar MOSFETs suffer minimal performance degradation due to parasitic resistance.

FinFETs
FinFETs, a 3D transistor design, introduce vertical fins with the gate wrapping around them for improved control. However, the effective contact width decreases relative to the gate width, leading to (W_C / W_G \approx 1/3). Consequently, the parasitic resistance becomes comparable to the channel resistance ((R_{EXT} / R_{ch} \approx 1)), which begins to impact the performance of the device as it scales.

Gate-All-Around (GAA) FETs
Gate-All-Around (GAA) FETs, which use nanosheets or nanowires, offer even better electrostatic control by fully surrounding the channel with the gate. However, the contact width further decreases compared to the gate width, resulting in (W_C / W_G \approx 1/6). This causes a significant increase in parasitic resistance, with (R_{EXT}) being approximately three times the channel resistance ((R_{EXT} / R_{ch} \approx 3)). While GAA FETs improve transistor density, the higher parasitic resistance becomes a challenge for maintaining performance.

Complementary FETs (CFETs)
Complementary FETs (CFETs) take transistor stacking to the next level by vertically integrating NMOS and PMOS transistors. This approach maximizes space efficiency in advanced nodes but inherits the high parasitic resistance of GAA FETs. With (W_C / W_G) remaining small, the (R_{EXT} / R_{ch}) ratio is around 3, posing similar challenges to those faced by GAA FETs.

Explanation of Parasitic Resistance

![image](https://github.com/user-attachments/assets/83c7943c-1a39-49d8-8619-b924c5929ef9)

The image highlights the breakdown of parasitic resistance ((R_{EXT})) and approaches for reducing it in transistors. Here is a detailed explanation:

Components of Parasitic Resistance ((R_{EXT})) The leftmost diagram illustrates the various contributors to (R_{EXT}) in a transistor:
(R_{CA-BEOL}): Resistance from the contact in the Back-End-Of-Line (BEOL).
(R_{CA}): Resistance at the contact area.
(R_{CA-TS}): Resistance at the contact to the transition structure.
(R_{TS}): Resistance in the transition structure.
(R_{MOL}): Middle-Of-Line resistance (includes lateral and vertical contributions).
(R_C): Contact resistance at the metal-semiconductor interface.
(R_{EPI}): Epitaxial layer resistance (contributes to current spreading).
(R_{FEOL}): Front-End-Of-Line resistance from the source/drain extensions.

Initial vs. Improved (R_{EXT}) Breakdown The two pie charts in the center show the contributions of different resistance components for NFETs and PFETs before and after improvements:
NFET:
Initial: Majority of (R_{EXT}) comes from (R_C) (63%) and (R_{CA-BEOL}) (31%).
Improved: Significant reduction in (R_C) (48%) and (R_{CA-BEOL}) (12%).
PFET:
Initial: (R_{FEOL}) (50%) and (R_C) (45%) dominate.
Improved: Major reduction in (R_{FEOL}) (78%) and (R_C) (16%).
Improving Ohmic/Tunneling Contacts The right section discusses methods to improve the metal-semiconductor interface:

Key Objectives:

Low Schottky Barrier Height (SBH) ((\phi_b)): Reduces the energy barrier for carrier injection, enabling better contact conductivity.
High Doping Concentration ((N_d)): Increases carrier density at the interface, reducing contact resistance.
Equation for Specific Contact Resistivity ((\rho_c)): [ \rho_c \propto \exp\left(\frac{2\phi_b}{\hbar} \sqrt{\frac{\epsilon_s m_x}{N_d}}\right) ] This equation shows how lowering (\phi_b) and increasing (N_d) can reduce (\rho_c).

Metal-Semiconductor Energy Diagram:

The energy diagram shows how a reduction in (\phi_b) (Schottky Barrier Height) facilitates easier carrier injection from the metal to the semiconductor.

![image](https://github.com/user-attachments/assets/21303e9f-fa48-4ebf-abc3-5db4706304a1)

The bar chart on the left shows how the composition of (C_{eff}) evolves from 22nm to 7nm technology nodes:

At 22nm, the dominant contributor to (C_{eff}) is (C_{fr}) (56%), while parasitic capacitances (C_{pc-ca}) (25%) and (C_{g}) (19%) contribute less.
At 14nm and 10nm, parasitic capacitances ((C_{pc-ca}) and (C_{fr})) start dominating, with (C_{fr}) decreasing to 38% and 25%, respectively, while (C_{pc-ca}) increases.
At 7nm, (C_{g}) becomes the most significant contributor (45%), with (C_{pc-ca}) and (C_{fr}) still present but reduced. This highlights the increasing impact of parasitic capacitance as node sizes shrink.

Plot Descriptions:

The first scatter plot shows a reduction in normalized delay for a ring oscillator when using SiBCN spacers instead of SiN spacers, indicating improved performance.
The second scatter plot demonstrates an 8% reduction in (C_{eff}) with SiBCN spacers, which corresponds to the delay improvement observed in the first plot.
The rightmost figure shows the evolution of spacer materials from SiOCN to SiCO. This material transition aims to significantly reduce the gate-contact capacitance across nodes. At 14nm and beyond, low-(k) spacers improve performance by decoupling parasitic effects and maintaining capacitance at manageable levels.
The bottom middle image shows a cross-sectional TEM view of a transistor with air spacers around the gate: i) Air, with its extremely low dielectric constant ((k \approx 1)), significantly reduces parasitic capacitance. The adjacent plot quantifies this improvement, showing a 15% reduction in (C_{eff}) when using air spacers compared to solid spacers.

![image](https://github.com/user-attachments/assets/ede2177f-232b-4ad3-88af-617c7499e483)

Key Properties of 2D Layered Materials (Compared to Silicon):

Uniform Atomic Scale Thickness: A single layer of MoS₂ is approximately 0.65 nm thick, offering an ideal thickness for scaling compared to silicon.
Higher Effective Mass (( m^ )):* MoS₂ has an effective mass of about 0.55 times the mass of a free electron (( m_0 )), whereas silicon’s effective mass is around 0.22 ( m_0 ).
Bandgap: Additionally, 2D materials like MoS₂ possess favorable bandgaps for electronic devices, with a monolayer bandgap of ~1.85 eV, which reduces to ~1.5 eV for a bilayer.

![image](https://github.com/user-attachments/assets/7f8a3229-945e-47fb-8e5f-47be4a9eb62d)

Transistor Scaling:

To achieve smaller gate lengths, devices must address various physical and material constraints to ensure reliable operation.
Challenges for Scaling:

Direct Source-to-Drain Tunneling: As the gate length decreases, electrons can tunnel directly from the source to the drain, bypassing the gate control. To mitigate this, materials with a high effective mass (( m^* )) are needed.
Surface Roughness and Thickness Variations: Variability at atomic scales can cause performance issues. Uniform, atomically thin materials are essential for minimizing such variations.
Capacitance Ratios (( C_D ) and ( C_{ox} )): The capacitance of the depletion region (( C_D )) must remain low relative to the gate oxide 
capacitance (( C_{ox} )) to improve gate control. Materials with a low in-plane dielectric constant (( \epsilon )) are necessary for this.

Diagrams:

The left shows the transistor structure with key components like the source, drain, gate, oxide, and silicon substrate.
The right illustrates two scenarios:
a. Thermionic Emission: Electrons cross the energy barrier as intended.
b. Direct Tunneling: At extremely small gate lengths, electrons tunnel directly from source to drain, leading to leakage.
Key Takeaway:

New channel materials, such as 2D materials, are required to overcome these challenges while maintaining high performance and scalability.

![image](https://github.com/user-attachments/assets/15be55b1-1eb4-489a-a93d-150aee591164)

Concept of Direct Source-to-Drain Tunneling: As the gate length ((L_G)) in MOSFETs decreases, direct tunneling of electrons from the source to the drain becomes significant, leading to increased leakage currents. This leakage is influenced by material properties, such as the effective mass ((m^*)) and the bandgap ((E_G)).

A higher (m^) in MoS₂ suppresses tunneling leakage compared to silicon. The graph shows the leakage current ((I_{SD, \text{leak}})) as a function of gate length ((L_G)) for various channel thicknesses ((T_{CH})). MoS₂ exhibits lower leakage at smaller gate lengths compared to silicon, achieving up to 100x reduction in leakage due to its higher (m^), larger (E_G), and lower dielectric constant ((\epsilon)).

The superior performance of MoS₂ in minimizing leakage currents results in significant energy savings, making it a promising material for future transistor scaling.

![image](https://github.com/user-attachments/assets/051cc6c5-f666-400b-91e4-d8010db1353a)

The MoS₂ transistor with a 1 nm gate length represents a breakthrough in miniaturization, featuring a thin MoS₂ channel for its excellent electronic properties. A single-walled carbon nanotube (SWCNT) serves as the ultra-small gate electrode, while Zirconium Dioxide (ZrO₂) acts as a high-k dielectric, reducing leakage and ensuring precise control. Built on a SiO₂ substrate with an n⁺ silicon back gate, the transistor uses the CNT gate to deplete a small region of the MoS₂ channel, enabling efficient modulation. This innovative design showcases the potential of 2D materials and nanoscale gates in advancing transistor technology.

![image](https://github.com/user-attachments/assets/ee8900a4-a9ff-4d5f-abbe-5437549afd85)

Semiconductor Field-Effect Transistor), where all key components, including the channel, gate, and contacts, are made using two-dimensional materials. This device leverages the exceptional properties of 2D materials to improve performance and scalability. Below is a breakdown of the key components and the fabrication process:

Graphene Contacts (S, D, G): Graphene is used as the source, drain, and gate electrodes. Its high conductivity and 2D nature make it ideal for ensuring low-resistance electrical contacts. MoS₂ Channel:

Molybdenum Disulfide (MoS₂) serves as the semiconductor channel. MoS₂ is widely used in 2D MOSFETs due to its excellent on/off current ratio and atomic-scale thickness. h-BN Dielectric:

Hexagonal Boron Nitride (h-BN) acts as the insulating dielectric layer. It is a 2D material with excellent insulating properties and high thermal stability, making it suitable for separating the graphene gate from the MoS₂ channel. Si/SiO₂ Substrate:

The device is fabricated on a silicon dioxide (SiO₂) layer on top of a silicon substrate, which provides mechanical support and a global back gate. Fabrication Process:

A layer of graphene is deposited on the SiO₂ substrate, which will later serve as the gate electrode.
Graphene is patterned to define the source and drain regions, leaving gaps for the channel.
A monolayer of MoS₂ is transferred onto the patterned graphene, forming the channel region.
An h-BN layer is added on top of the MoS₂ as the gate dielectric.
A top layer of graphene is deposited and aligned as the gate electrode.
The completed device is contacted using metallic electrodes (Ni/Au) for testing.

![image](https://github.com/user-attachments/assets/1ac91246-07f0-4cab-b510-d446b2a1e19f)

The All-2D MOSFET exhibits excellent electrical performance:

Transfer Characteristics (I(_D) vs V(_G)): Achieves a high on/off current ratio (>10⁵), demonstrating strong gate control for effective switching.
Output Characteristics (I(D) vs V({DS})): Smooth current modulation with increasing V(G) and V({DS}), indicating good output performance.
Mobility: Field-effect mobility remains constant with increasing gate electric field, showing minimal scattering and high-quality interfaces in the 2D materials stack.
These results highlight the potential of 2D materials like MoS₂, graphene, and h-BN for scalable, high-performance transistor applications.

![image](https://github.com/user-attachments/assets/7fcb26b9-bf2e-40a4-bfaa-df25c0d5ae0c)

The diagram on the top left shows a non-planar transistor with key components:

Gate: Controls the flow of current through the channel.
Channel: Region where current flows between the source (S) and drain (D).
Body: Underlying region connected to the substrate.
STI (Shallow Trench Isolation): Insulates neighboring devices.
The biggest challenge is to form a single-crystalline semiconductors on a non-planar surface is difficult using conventional semiconductor fabrication techniques.

![image](https://github.com/user-attachments/assets/6a464a19-962b-4581-b037-9904d4f83be9)

Single-Layer CMOS (a): This is the traditional CMOS design where NMOS and PMOS transistors are fabricated on a single silicon layer. Each transistor operates in the same planar layer, with devices connected laterally.

Monolithic 3D CMOS (b): In this design, NMOS and PMOS transistors are stacked in two separate layers, enabling higher density. The P-Channel (PMOS) is placed on top of the N-Channel (NMOS), separated by an oxide layer. This approach reduces the footprint and allows better performance due to shorter interconnects.

Single-Layer CMOS Logic (c): Shows logic gates (inverter, 2-input NAND, and 2-input NOR) built using traditional single-layer CMOS. Transistors are laid out horizontally, with interconnections taking more space.

Monolithic 3D CMOS Logic (d): Logic gates are constructed with two transistor layers (Layer 1 and Layer 2), reducing the area required for interconnections. Vertical integration improves performance and reduces delay by shortening signal paths.

![image](https://github.com/user-attachments/assets/fa40cc99-28a1-4795-997a-a82a687d224e)

Dual Damascene Cu, used for the 7nm technology node with a 36nm pitch, combines vias (vertical connections) and lines (horizontal connections) in a single patterning step. It relies on copper (Cu) for interconnections; however, as dimensions shrink, challenges such as gap filling and maintaining reliability become increasingly significant.

Single Damascene Cu, used for the 5nm technology node with a 28nm pitch, involves splitting the creation of vias (vertical connections) and lines (horizontal connections) into separate steps. This approach addresses the challenges of smaller dimensions, with a primary focus on reducing resistance (R) in both lines and vias to maintain optimal performance.

Barrier and via metal optimization, introduced at the 3nm technology node with a 20-24nm pitch, focuses on reducing the thickness of barrier layers (insulating layers) to minimize resistance while maintaining robust and reliable via connections. This optimization is essential to meet the performance and scaling demands of advanced nodes.

At sub-18nm pitch, subtractive RIE and alternative metals like ruthenium (Ru) are introduced to address the reliability and scaling challenges faced by traditional copper interconnects. Subtractive Reactive Ion Etching (RIE) enables more precise patterning of interconnects, while the use of Ru provides improved performance and durability at such advanced dimensions.

For future nodes with pitches below 15nm, post-Damascene interconnects featuring tall, barrier-less designs are envisioned. This approach enhances electromigration (EM) reliability, ensuring durable and robust connections despite the continued shrinking of dimensions, thereby addressing key challenges in advanced interconnect scaling.

![image](https://github.com/user-attachments/assets/6ed30d62-cf75-457e-a582-303659e5888b)

The image shows how a selective barrier, typically tantalum nitride (TaN), can improve copper interconnects in semiconductor manufacturing. This barrier reduces resistance, enhances reliability by preventing copper ion migration, and aids in controlling copper thickness. The process involves cleaning the copper surface, depositing TaN using atomic layer deposition (ALD), and removing sacrificial layers. This technique is crucial for advancing semiconductor technology and ensuring reliable, high-performance devices.

![image](https://github.com/user-attachments/assets/feff2b83-a47f-4953-b8ed-2bf4d64460a7)

Back-Side Power Delivery Network (BS-PDN)

In advanced semiconductor manufacturing, efficient power delivery is critical to the performance and reliability of integrated circuits. Traditional Front-Side Power Delivery Networks (FS-PDNs) often suffer from high IR-drop, which can limit device performance and reliability. To address this challenge, Back-Side Power Delivery Networks (BS-PDNs) have emerged as a promising solution.

BS-PDNs involve routing power supply rails on the backside of the chip, enabling shorter and wider power lines. This configuration significantly reduces IR-drop, leading to improved power delivery efficiency. As a result, BS-PDNs offer several advantages:

Reduced IR-drop: Lower voltage drops across the power network, leading to improved performance and reliability.
Decreased standard cell area: More efficient power delivery allows for smaller standard cell sizes.
Improved performance: Lower IR-drop leads to faster switching speeds and reduced power dissipation.
By adopting BS-PDNs, semiconductor manufacturers can develop high-performance and energy-efficient integrated circuits that meet the demands of modern electronics

Section 2:- Tools Installation.

git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts
cd OpenROAD-flow-scripts
sudo ./setup.sh

./build_openroad.sh --local

Verify Installation

source ./env.sh
yosys -help
openroad -help
cd flow
make

make gui_final

Section 3:- Flow Structure.

OpenROAD Directory Structure and File formats

├── OpenROAD-flow-scripts             
│   ├── docker           -> It has Docker based installation, run scripts and all saved here
│   ├── docs             -> Documentation for OpenROAD or its flow scripts.  
│   ├── flow             -> Files related to run RTL to GDS flow  
|   ├── jenkins          -> It contains the regression test designed for each build update
│   ├── tools            -> It contains all the required tools to run RTL to GDS flow
│   ├── etc              -> Has the dependency installer script and other things
│   ├── setup_env.sh     -> Its the source file to source all our OpenROAD rules to run the RTL to GDS flow

Now, go to flow directory

├── flow           
│   ├── design           -> It has built-in examples from RTL to GDS flow across different technology nodes
│   ├── makefile         -> The automated flow runs through makefile setup
│   ├── platform         -> It has different technology note libraries, lef files, GDS etc 
|   ├── tutorials        
│   ├── util            
│   ├── scripts             

Section 4:- Automated RTL2GDS Flow for VSDBabySoC.
This is done by seeing the workshop video.

Initial Steps:

We need to create a directory vsdbabysoc inside OpenROAD-flow-scripts/flow/designs/sky130hd
Now copy the folders gds, include, lef and lib from the VSDBabySoC folder in your system into this directory.
The gds folder would contain the files avsddac.gds and avsdpll.gds
The include folder would contain the files sandpiper.vh, sandpiper_gen.vh, sp_default.vh and sp_verilog.vh
The lef folder would contain the files avsddac.lef and avsdpll.lef
The Additional lib folder would contain the files avsddac.lib and avsdpll.lib

Now copy the constraints file(vsdbabysoc_synthesis.sdc) from the VSDBabySoC folder in your system into this directory which we used previously for the above lab work.
Now copy the files(macro.cfg and pin_order.cfg) from the VSDBabySoC folder in your system into this directory or else in the config.mk file use the dia and core area command, it will automatically places the macros

Section 5:- OpenROAD GUI. & Section 6:- Macro Placement RTL MP and QOR.
Here in both the section we just opened the gui file of gcd design of nangate45 platform and ariane136 design, which we run the make command and after once it is fully completed then we opened the gui of floorplan, placement, cts, route, final. The commands are:-

# Assuming you should be inside the OpenROad directory inside flow folder then run below commands.
make # by default makefile will have the gcd as the default design
# or
make DESIGN_CONFIG=./designs/nangate45/gcd/config.mk
make DESIGN_CONFIG=./designs/nangate45/ariane136/config.mk
make gui_floorplan
make gui_place
make gui_cts
make gui_route
make gui_final
# or we can open the gui file and their we select the .odb file going through the results folder of nangate45 platform
source ./env.sh # go to the OpenROAD directory then run this command then below command
openroad -gui
make metadata
gedit designs/nangate45/gcd/metadata-base-ok.json

Section 7:- Design exploration using Autotuner.
Go to the given link of OpenROAD documentation their you will get how to use it

https://openroad-flow-scripts.readthedocs.io/en/latest/user/InstructionsForAutoTuner.html#.

pip3.9 install -U --user 'ray[default,tune]==1.11.0' ax-platform hyperopt nevergrad optuna pandas
or if above not works then use below
python3.9 -m pip install -U --user 'ray[default,tune]==1.11.0' ax-platform hyperopt nevergrad optuna pandas

pip3.9 install -U --user colorama==0.4.4 bayesian-optimization==1.4.0
or 
python3.9 -m pip install -U --user colorama==0.4.4 bayesian-optimization==1.4.0

cd flow/util/
python3 distributed.py tune -h
python3 distributed.py --design gcd --platform sky130hd \
                       --config ../../../../flow/designs/sky130hd/gcd/autotuner.json \
                       tune
                       or if above not works then use below
python3.9 distributed.py --design gcd --platform sky130hd \
                       --config ../../../../flow/designs/sky130hd/gcd/autotuner.json \
                       tune --samples 5
                       
tensorboard --logdir=../logs/sky130hd/gcd/test-tune-__date__/

Section 8 & Section 9 :-
This section is all about the updating any issue is found in openroad and opensta resolve it and update it to the git hub.
Opensta.

cmake .
make -j27
test/regression
time test/regression
gedit verilog/VerilogReader.cc
make
time test/regression
cd test/results/
ls
cat delay_calc.log

OpenROAD.

git clone https://github.com/CHANDANKUMARNS07/OpenROAD-flow-scripts.git
cd OpenROAD-flow-scripts
cd flow
# go into the asap7 design and also open gcd.v file in src folder 
cd ../../
make DESIGN_CONFIG=./designs/asap7/gcd/config.mk 
#see the 4_1_cts.log their the time 
#and change the cts.tcl file by adding two commands
#before executing below command first clear the previous results otherwise it will be of no effect
make DESIGN_CONFIG=./designs/asap7/gcd/config.mk 
cd ..
git status
git add .
git commit -a -m "cts file has been updated with :? operator"
git push
git diff

By using the above workshop knowledge we use the OpenROAD opensource tool for running our vsdbabysoc which we used in previous labs.
As already defined the flow structure in the section 3 of this lab i will follow the same structure.

At first we make the design folder named VSDbabySOC_chandan inside the designs folder.
And all the files are included as per the flow structure.
The below is the config.mk file.

make # when you change in make file use this command or else use below command in flow directory
make DESIGN_CONFIG=./designs/sky130hd/VSDbabySOC_chandan/config.mk
make gui_floorplan
make gui_place
make gui_cts
make gui_route
make gui_final

export DESIGN_NICKNAME = VSDbabySOC_chandan
export DESIGN_NAME = vsdbabysoc
export PLATFORM    = sky130hd


export ADDITIONAL_LIBS = $(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/lib/avsddac.lib \
		$(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/lib/avsdpll.lib

export VERILOG_FILES =	$(DESIGN_HOME)/src/$(DESIGN_NICKNAME)/vsdbabysoc.v \
	$(DESIGN_HOME)/src/$(DESIGN_NICKNAME)/riscv_chandan.v \
	$(DESIGN_HOME)/src/$(DESIGN_NICKNAME)/include/clk_gate.v 
		  
export VERILOG_INCLUDE_DIRS = $(DESIGN_HOME)/src/$(DESIGN_NICKNAME)/include

export SDC_FILE      =  $(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/constraint.sdc

export ADDITIONAL_LEFS = $(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/avsddac.lef \
		$(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/avsdpll.lef

export GDS_FILES  = $(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/gds/avsddac.gds \
	$(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/gds/avsdpll.gds 


export MACRO_PLACEMENT = $(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/macro.cfg
export DIE_AREA = 0 0 3000 3000
export CORE_AREA = 50 50 2900 2900
export REMOVE_ABC_BUFFERS = 1

entire flow in a one go and checked the floorplan, placement, cts, routing and final gui separately by running the below commands:-

make gui_floorplan
make gui_place
make gui_cts
make gui_route
make gui_final

Heatmap
In physical design of semiconductor chips, a heatmap is a visual representation that shows the distribution of a particular parameter (such as power, temperature, or congestion) across the chip's layout. It uses color coding to represent varying values of the parameter, with each color corresponding to a specific range or intensity of that parameter. Heatmaps are used to provide a quick, intuitive understanding of how different regions of the chip are behaving with respect to specific design goals or constraints.
The heatmap of the design can be found using:

make gui_place




