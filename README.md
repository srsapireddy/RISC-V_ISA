# RISC-V_ISA

### Introduction to RISC-V Basics
#### RISC-V Instruction Set Architecture
This is the way we are going to talk to the computers. Suppose we need a C program to run on a computer/ hardware with a particular layout (interior of the chip present inside the laptop). The C program is first compiled into assembly program language, which is nothing but the RISC-V assembly language program. This assembly language program is converted into the machine language program in the form of a binary language program, which is understood by the hardware of the computer present in the hexadecimal format. 

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/03e27285-21d4-4cc2-9e6e-59d8737b10c5) </br>

We need to implement the RISC-V specification present in C language into some RTL. From RTL to layout, it is called the standard PnR flow (RTL to GDS flow). The entire flow starts from the RISC-V architecture. And implemented in RTL and RTL to the layout.

#### From Applications to Hardware

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c8ad70e5-8717-4b0d-a4df-2c55a4524b0f) </br>

The system software converts the application software into binary language to be executed on the hardware. The major components of the system software are the OS, compiler, and assembler. The compiler converses the respective C programming language code into the particular instruction set architecture with respect to the hardware. Thus, the output of the compiler is dependent on the hardware. This is in .exe format. The assembler's job is to take the instructions and convert them into the binary format. Basically, it is called a machine language program. The hardware generates the outputs according to the machine language program input, which is in the form of binary numbers. 

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/35cc4f60-4d35-4342-92c9-37517bf18b57) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/175a5d1d-b648-4562-88d4-1e3ccc60af58) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3fe721ff-3bce-4213-94e1-907ae51680c7) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/74580d17-1b12-4a51-9b05-fc210fa6af70) </br>

The instruction acts as the abstract interface between the C program and the hardware. This is called the Instruction Set Architecture or called the Architecture of the computer. The hardware only understands only 1’s and 0’s as inputs. We need a Hardware Description Language that implements particular specifications. This is called the RTL implementation of the specifications. The RTL here is synthesized into the netlist. Then, we do the Physical Design implementation of the Synthesized netlist of the RTL.  

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e1f8f06a-e73c-4ac7-9ee2-60aafd9264cf) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/47943449-4885-4ae9-813c-ae987c37c47e) </br>

### Basics
We will start with integer addition and multiplication. 

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/30c3404b-ddf9-484c-91b6-55c946cdfdfc)

Output of the compiler:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/8c8604e1-629e-4727-b860-a79f9ed8611e)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/220b3faa-7abe-4f6e-96d5-524391973f25)

Any CPU core should contain the base integer instructions.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/39975ad4-f45d-4f4e-911c-a18b4a2f49ed)

Multiply extension instructions:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b8f01b13-bd7c-41da-adc3-21efb50c1bc9)

Single and double precision floating point extensions:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/8a2f8537-bd13-4338-a854-f4d080b92f71)

These registers can be accessed by the application programmers directly. These are system call functions.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e32ade62-33f1-4506-ad99-b24c2ad051f1)

There is some data transfer between the registers and memory. This is called the Memory allocation and stack pointer.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/0cf72672-b250-42be-83ae-f5cec3d09e45)

### Labwork for RISC-V
#### C Program to Compute Sum From 1 to N
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/56542919-b5e8-4511-8cbf-be2a96113877)
Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/947c4cce-b940-4dd1-861a-5eb529815054)

#### RISCV GCC Compile and Disassemble
Compiling the same code with RISC-V gcc compiler:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/9226d880-fc09-45a7-bc17-f7c950b112c1)

Assembly code for which we are trying to run the C program:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/2e12d157-75e9-4c2b-8a66-07bfc22dc0fe)

15 instructions came out when we the options -o1 and other options.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c043ad04-be08-405e-ab40-fa659aba1135)
### Correct Output: Use -O1 instead of -o1
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c0874ae5-e380-4080-8316-20a2e8c95e88)

Running the command with different options:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/54a05cf8-a28a-4a9f-b426-22a33e0194c4)

#### Spike Simulation and Debug
To check if the simulations are as expected 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/639ffa8f-9364-4bcc-8a00-8c8cae92e62d)

To debug: open up the object file of the dump
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/af276f4a-8834-4f4b-b350-d0261de6d823)
To debug all the things in the dump file, we need to open a debugger
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/217e5f31-29c1-44d3-8d47-e9388336848d)
Contents of a2 are in 64-bit:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/59fc8074-9c74-4a08-856f-5545465e806d)
Press enter to run the next instruction. This shows that the next instruction has been executed. This shows the value content in the register a5
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e560b951-547e-42b2-b26d-9b36e643b45c)
lui - load upper immediate
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/8bb57dd2-ce49-41c4-8adf-3ec29577301b)
Checking the value in the stack pointer register
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b940adee-f86c-48f7-9896-0739d13ce98f)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/8fffcf02-4d83-44a9-b161-037bf7a32199)
addi - add immediate
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/cf86ccae-b3bd-4fd2-a154-884067c2be8f)

### Integer number representation
#### 64-bit Number System for Unsigned Numbers
There has to be an interface that converts humans' understanding of decimal format to computers' understanding of binary format. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/dda3db1c-d95c-4556-a604-8539e43a8ce9)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d8869fb2-c2ba-4936-bc21-2ad9ce16338f)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/f09e0e73-abea-435b-8ae5-8eee4fc47186)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/2c1a269d-64d6-4013-a386-9eccb65b2a2a)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/7d6058be-2494-4b94-a4cd-17f5a634c3c6)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3407b46a-448c-4d49-b6d7-474c497cdede)

#### 64-bit Number System for Signed Numbers
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6283f68b-9450-4eb5-999d-b89a8ad79c6a)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/04042667-e244-4966-b969-9d555f64b238)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/2ff6bc55-80f9-4a68-847b-723c85d9a0fa)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/f98d5e90-9a6f-47e6-a560-35ecc0269f57)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/eef32a3e-9fff-4994-b4ac-7003401744f8)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/57d647db-ffdf-47ca-9326-797be50d80cc)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6a93caf1-b821-49e7-bc1a-cf18104fa31d)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ed025f73-4b15-4929-865b-4d08d16820c4)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/53a0c171-8af6-45c5-b3f3-63390850b827)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/192ae701-6ab6-4e96-8353-fe2391ccc417)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6ee5d459-e8d3-4dab-9cb2-762e4905c6f5)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/2ac7f8e7-02da-4d8b-8283-bdd8083cafa8)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e3decd4e-a26a-47f5-9f33-3dc1d11d39b5)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d515a382-b50b-486f-9031-6c8dc628b2a3)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/aeb79849-e565-4ead-b77b-c951dc1f9688)

#### Unsigned and Signed Numbers Lab
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/de8d466c-bfa9-45c5-8277-9d1dd2759fcf)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/a23a2311-009e-47da-9496-f9e915e1c5f3)
Check for the max value
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/aef2dc1c-2f6f-453c-8f6c-7c8337282622)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/dba94e83-5c42-4097-bd6f-4cd3cf1cc23f)
Example 2
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/cd71eb5a-1165-47e9-8cbd-9a64476f1d94)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/1a76749e-cd0c-4bb9-99e1-7cce313edd9f)

For Signed Number
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/70937750-4354-4107-85e3-5354211da773)
To represent Signed Number
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/a7a6a8c8-ca34-4c02-9b13-26df96de3374)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/1a74e228-bdfa-434a-a12e-745236d77737)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/be4ae7bf-c5b2-4cd1-98ef-bbcb6ba6af01)

### Introduction to ABI and Basic Verification Flow
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/f50b657f-ff4c-49fd-a953-08e46f24d3d4)
#### Introduction to Application Binary Interface
Interface Meaning:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ab1909f6-c284-43e1-824a-16d524a5fb79)
In terms of computers
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/90e6767c-2096-4288-a0e9-8223287ddc6b)
The ISA is accessible to the operating system and the user through standard libraries for the developer.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/8c1a7bb2-f132-4da9-a124-e8e241a99b83)
Some parts of ISA are available to the operating system, and some are available to the programmer directly. Those parts are defined as User ISA and User & system ISA.
The application program can access some operating system resources using system calls. The application program can access the registers of RISC-V architecture via system calls. This interface is called the Application Binary Interface.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/257b2bc4-fe30-46b2-9eee-33ba03f48ac4)
If the application programmer wants to access the system resources of the processor, this has to be done using the registers.
In RISC-V we got 32 registers
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ec8cb5b5-b32c-49b1-a373-a0f6590d5e5b)

#### Memory Allocation for Double Words
Why do we have only 32 registers?
Two ways to load values to registers:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e014b683-db92-47da-a616-b7e027851fef)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/1a762366-0ef8-427c-bba1-7d6b1772dd55)
Addresses are shown in green color.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/5824d51a-bae4-4ae7-97a0-939d82adb9b1)

#### Load, Add, and Store Instructions with Example
We are trying to load the data into X8 register
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/0739c01e-a9b4-4430-bf29-2b87cedb57e4)
We need the 1st address to get the value of the 16th address of the memory. The base address starts with 0 value
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/19c4b465-dff0-4214-b08f-cf14b257b728)
16(x23) forms the source address. Here, 16 gets added to the contents of x23 to form the final address.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/569a4854-1885-4923-a578-65ed16750c8b)
Representation of 16(x23) inside the computer. Here, 16 is the offset. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c0c12261-5ef1-45e2-870b-c0003f985246)
Example 2: add instruction
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/faa4768f-dde1-4a7d-b36b-77647004184b)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/5b415980-5455-479a-8140-08be072bc2ae)
Example 3: Storing back to memory. Here, 8 is the offset. Offset - where to start loading
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/bb2c0b80-f809-419d-a41c-db49e11fa5ca)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3fca7ce3-d486-4bcb-8a73-e9ceb4126459)

#### 32-Registers and their Respective ABI Names
There are a total of 47 base instructions
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/59fe5c85-4514-4cda-8ad9-dcf22ec3ad6e)
Add instruction operates on only registers. These types of registers are called R-type instructions.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/0b852c41-3e44-4f09-bf22-f21ac05449b1)
Instructions that operate on registers and immediate are called I-type instructions
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/8357ce6a-2dad-4bbc-9cee-dff52a6556f1)
sd operates only on the source registers and the immediate. This is for storing something. This type of instruction is called S-type instruction.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ebebc322-935d-4208-b19d-4e241b0df4e2)
All the registers accessed here are 5-bits
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/a8d68f90-685d-43ea-882c-a5bcd2d02be6)
ABI makes system calls using these 32 registers. Internal names of the registers to access these registers.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d3b679d6-4807-42cb-b93e-2333566b31fd)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/01a6bc53-c321-4b3c-ad3e-8c4eed77bcb3)

### ABI Lab
#### Study New Algorithm for Sum 1 to N Using ASM
Through the C program, we will make some function calls to the assembly language program in the RISC-V ISA. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/a9080c5d-13f2-4089-a756-b82c79e37ea8)
Here, the arguments are passed into registers a0, a1, and they will be returned to register a0. 
Algorithm: We can use any registers for a1 to a7
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/4765db0b-ba6c-4573-8d96-69a63504e3b4)

#### ASM Function Call
The main program that does the function call
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/23020006-2272-4a25-9a94-fedf63d64b07)
The function itself
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6cf367a8-399e-4e1e-b427-6dc14a98c241)

#### Simulating new C program with Function Call
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/f0f6a0b4-10ac-4c7f-a1a5-f7d3748e2332)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/151c97d7-7749-4656-a108-19ad84bbb483)
Theory:![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/9db5514b-c3da-4b86-b9f4-39105772d965)

### Basic verification flow using iverilog
#### Running C Program on RISC-V CPU
We convert this C program into HEX file format in memory to load into RISC-V CPU
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d9ef5b61-4d20-45b9-8f00-657f5577322d)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/617b607f-2c1b-4730-a5b0-2e1c888d2fdc)

Files Directory of PicoRV32
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/0c847554-fe54-4c14-9d3d-276600b90c54)
This creates a HEX file in binary format. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/be4933b1-ee19-42ca-a20c-0f457df73e4c)

### Digital Logic with TL-Verilog and Makerchip
Reference: https://github.com/stevehoover/RISC-V_MYTH_Workshop

#### Introduction to Logic Gates with TL-Verilog in Makerchip IDE
Logic Gates
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/9e65d893-d4d9-47e8-8b3d-40cb54a7ff7d)
Combinational Circuit: Full Adder Circuit
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/78b46030-0cba-4ba8-82f2-ddcbf6d70eb9)
Adder Circuit
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3da95cc5-a4c8-4ab1-8f23-e59e818aa160)
Boolean Operations
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/cf731aeb-140b-45c5-a51c-6d90801bae0e)

#### Basic Mux Implementation and Introduction to Makerchip
Multiplexer (MUX): Acts like a switch. Here, the Verilog represents a ternary operator.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3446cb12-8900-454f-8518-a05d1a45b5b2)
Changing Ternary Operator
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/389d9d75-36ab-4780-a8e8-ed2d459da5a6) </br>
Makerchip link: https://makerchip.com/ </br>
Pipelined FPGA Multiplier Example: </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d60eed37-63dd-4332-9e96-4b6ae75e30d3)
Link: https://makerchip.com/sandbox/00Rf2hDnr/0lOh4v

#### Labs for Combinational Logic
#### Exercise 1:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ada93032-494a-419f-af8e-6cfe2fdfcf3d)
##### Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ba5a18dd-4acf-438a-8be4-ace026c60625)

#### Exercise 2:
Initially, we started understanding the Makerchip IDE platform by trying some basic digital logic gates, with the inverter being the standard. In TL Verilog, we code the logic itself viz $out =!$in1 without declaring the variables separately, and $in an assignment is also not required. The output of the above is shown in the figure below. We note that simultaneous highlighting of the variable is possible at the output.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3292720d-199d-408a-b684-8d016b2f9cd7)
##### Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/62cf9d68-c44c-48ea-b295-b85918a09d33)
##### Code
```
\m5_TLV_version 1d: tl-x.org
\m5
   
   // =================================================
   // Welcome!  New to Makerchip? Try the "Learn" menu.
   // =================================================
   
   //use(m5-1.0)   /// uncomment to use M5 macro library.
\SV
   // Macro providing required top-level module definition, random
   // stimulus support, and Verilator config.
   m5_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $reset = *reset;
   
   $out = ! $in1;
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule

```

#### Exercise 3: Logic Gates and Vectors Lab
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/12fc1968-69da-4270-9b8b-d6828ea32e5d)
##### Vectors Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6f3f41b1-9d11-4dbc-adf3-fcf21f7633d2)

##### Logic Gates Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d2a7017c-4415-4df8-9320-6ff4877c76ad)
##### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   
   m4_makerchip_module
\TLV
   
   $reset = *reset;
   $out1 = $A & $B; // AND gate
   $out2 = $A | $B; // OR gate
   $out3 = $A ^ $B; // XOR gate
   $out4 = !($A & $B); // NAND gate
   $out5 = !($A & $B); // NOR gate
   $out6 = !($A & $B); // XNOR gate

   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule

```

#### Exercise 4: Mux
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/32e70599-7e5c-4b5a-aaf5-6ebecc0f435c)
##### Output 1:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/5a52f29e-f762-4f32-8c93-03e264438357)
##### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   
   m4_makerchip_module
\TLV
   
   $out = $sel ? $in1 : $in2;

   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule

```
##### Output 2:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/bef3bfc7-b27a-42ce-b3f2-3843de6b72cb)
##### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   
   m4_makerchip_module
\TLV
   
   $out[7:0] = $sel ? $in1[7:0] : $in2[7:0];

   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule

```


#### Exercise 5: Combinational Calculator
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b30398ac-9296-470c-a6d3-bab0aeccb9a8)
##### Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/fbee12ba-f5ee-4764-857d-79b72bdec3da)

##### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // TL-Verilog docs: http://tl-x.org
   // Tutorials:       http://makerchip.com/tutorials
   //m4_makerchip_module
      // To relax Verilator compiler checking:
      /* verilator lint_off UNOPTFLAT */
      /* verilator lint_off WIDTH */

   // =========================================
   // Welcome!  Try the tutorials via the menu.
   // =========================================

   // Default Makerchip TL-Verilog Code Template

   // Macro providing required top-level module definition, random
   // stimulus support, and Verilator config.
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $reset = *reset;
   
   //define smaller random numbers 4bit and assign to val1/val2
   // 31-4 bits of val1/val2 will be zero and 0-9 bits will be rand1/rand2
   //values
   $val1[31:0] = $rand1[3:0];
   $val2[31:0] = $rand2[3:0];
   $op[1:0] = $rand3[1:0];
   $sum[31:0] = $val1[31:0] + $val2[31:0];
   $diff[31:0] = $val1[31:0] - $val2[31:0];
   $prod[31:0] = $val1[31:0] * $val2[31:0];
   $quot[31:0] = $val1[31:0] / $val2[31:0];
   $out[31:0] =
         ($op == 0)
           ? $sum[31:0] :
         ($op == 1)
           ? $diff[31:0] :
         ($op == 2)
           ? $prod[31:0] :
         ($op == 3)
           ? $quot[31:0] :
         //default
           32'b0;

   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;

\SV
   endmodule
```

### Sequential Logic
#### Introduction to Sequential Logic and Counter
First, the Fibonacci series is discussed, and the single line code $num[31:0] = $reset ? 1 : (>>1$num + >>2$num); implementing it is written. Here, the concept of ahead operator >>1 and >>2which provides the output 1 cycle and 2 cycles before, comes into the picture. Next, a free-running counter is designed using the ahead operator concept. The snapshot of the free-running counter is as shown.
##### Sequential Logic: D Flip Flop
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3ec173f0-f437-4a31-92ea-ddc1bb5e6a55)
Sequential Logic as State Machine
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/4b222f4c-dfa4-461d-9b57-cc6846cf7072)
###### 1. Fibonacci Series
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b263752b-5ae8-4fc6-ae09-6a3f8348d67a)
###### 2. Fibonacci Series with the Reset
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6a82b251-c4c7-493c-8ac2-777eaa558d83)
###### 3. Counter Lab
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/82947e04-cf81-4bb9-a13c-dad86de9078c)
##### Output: 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3fa46299-a8c7-4ff8-b25e-9acac5b6b967)
##### Link: [https://makerchip.com/sandbox/#](https://makerchip.com/sandbox/00Rf2hDnr/0nZhB0)
##### Code:
```
\m5_TLV_version 1d: tl-x.org
\m5
   
   // =================================================
   // Welcome!  New to Makerchip? Try the "Learn" menu.
   // =================================================
   
   //use(m5-1.0)   /// uncomment to use M5 macro library.
\SV
   // Macro providing required top-level module definition, random
   // stimulus support, and Verilator config.
   m5_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   //$reset = *reset;
   
   $cnt[15:0] = $rest ? 0 : >>1$cnt + 1;
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule

```

#### Sequential Calculator 
##### Expressing constant values in Verilog
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e297e8ac-eec1-40c2-bb36-e09b3a29626d)
##### Sequential Calculator
Starting with basic example in sequential logic is Fibonacci Series with reset. To write the logic of Series using TL-Verilog, is $num[31:0] = $reset ? 1 : (>>1$num + >>2$num). This operator >>? is ahead of the operator, which will provide the value of that signal 1 cycle before and 2 cycles before, respectively. Below is a snapshot of the Sequential Calculator, which remembers the last result and uses it for the next calculation.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/53f13b4b-7747-49c5-acf9-c5adec1338b6)
##### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/9e104a6e-0c77-499c-9adc-94c25064be1d)
##### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found at: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/bd1f186fde018ff9e3fd80597b7397a1c862cf15/tlv_lib/calculator_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)

\TLV
   |calc
      @0
         $reset = *reset;
         
         
         $val1[31:0] = >>1$out[31:0];
         $val2[31:0] = $rand2[3:0];
         $op[1:0] = $rand3[1:0];
   
         $sum[31:0] = $val1[31:0] + $val2[31:0];
         $diff[31:0] = $val1[31:0] - $val2[31:0];
         $prod[31:0] = $val1[31:0] * $val2[31:0];
         $quot[31:0] = $val1[31:0] / $val2[31:0];
   
         $out[31:0] = $reset ? 32'b0 : (($op[1:0]==2'b00) ? $sum :
                                       ($op[1:0]==2'b01) ? $diff :
                                          ($op[1:0]==2'b10) ? $prod : $quot);
                      
         

      // Macro instantiations for calculator visualization(disabled by default).
      // Uncomment to enable visualisation, and also,
      // NOTE: If visualization is enabled, $op must be defined to the proper width using the expression below.
      //       (Any signals other than $rand1, $rand2 that are not explicitly assigned will result in strange errors.)
      //       You can, however, safely use these specific random signals as described in the videos:
      //  o $rand1[3:0]
      //  o $rand2[3:0]
      //  o $op[x:0]
      
   //m4+cal_viz(@3) // Arg: Pipeline stage represented by viz, should be atleast equal to last stage of CALCULATOR logic.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   

\SV
   endmodule
```
#### Pipelined Logic
##### Pipelined Logic and Re-Timing
###### Simple Pipeline
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/474bda0a-6f47-4b08-870f-f92b0bfa0857)
###### Simple Pipeline - Timing Abstract
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/7fbd54f6-6069-46d7-85d1-787e3c500e5b)
##### TL-Verilog Code
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6bad1d8e-2495-456c-92e0-f1e4ce38e545)
##### System Verilog vs TL-Verilog
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/360ff3a2-8e3f-49d7-be66-008362bb0436)
TL-Verilog has code reduction compared to System Verilog
##### Code Reduction - Timing
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e33fcef7-a297-4934-9a8b-e8f41db69671)
The timing does not impact the overall behavior in TL-Verilog using Pipelining by changing the stage bucketing. If we want to spread logic in more stages, it is possible. It helps to propagate the signals in the silicon wafer from one corner to another. 
##### Retiming in System Verilog
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/115e8285-c5c9-4dc8-894a-8cee706ea214)

#### Pipeline Logic Advantages
Pipelining or timing abstract is an important feature in TL Verilog as it can be implemented very easily with fewer codes as compared to system Verilog, which reduces bugs to a great extent. An example of the pipeline for Pythagoras' theorem using TL verilog and system verilog is shown here. In TL, the Verilog pipeline can be implemented by defining the pipeline as |calc, and the different pipeline stages should be properly aligned and indicated by @1, @2, and so on.

Below, the snapshot of the pipeline sequential calculator is included. Here, the first pipeline stage consists of the input followed by an arithmetic operation in the second pipeline stage, and finally, the output is included 2 cycles ahead in the third pipeline stage.

Timing abstract is a powerful feature of TL-Verilog, which easily converts a code into pipeline stages. Whole code under |pipe scope with stages defined as @? Below is a snapshot of Counter and Calculator in Pipeline & 2-Cycle Calculator, which clears the output alternatively, and the output of given inputs is observed at the next cycle.

##### High Frequency
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/51d5fd11-63d0-4a68-af31-926421ba0eb9)
We can run the design at a higher clock by pipelining the design. So, if we run our clock faster, we can produce more data and high throughput. 
##### Example
When we are pipelining the design, we are distributing the design in time. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/05ec8b39-de0a-4709-a213-53fd6c9ca6b3)

#### 2 Cycle Calculator Example
##### In 1 cycle
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/fa15f237-68c2-47a0-b7e3-0d1ad105747d)
##### Counter and Calculator in a Pipeline
##### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/447d839e-4327-4329-9563-c83747834e14)
#### Code
```
\m4_TLV_version 1d: tl-x.org
\SV

   // =========================================
   // Welcome!  Try the tutorials via the menu.
   // =========================================

   // Default Makerchip TL-Verilog Code Template
   
   // Macro providing required top-level module definition, random
   // stimulus support, and Verilator config.
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   //$reset = *reset;
   
   |calc
      @0
         $reset = *reset;
         
      @1
         $val1 [31:0] = >>1$out [31:0];
         $val2 [31:0] = $rand2[3:0];
   
         $sum [31:0] = $val1 + $val2;
         $diff[31:0] = $val1 - $val2;
         $prod[31:0] = $val1 * $val2;
         $quot[31:0] = $val1 / $val2;
         
         $out [31:0] = ($reset ? 0 : ($op[0] ? $sum : ($op[1] ? $diff : ($op[2] ? $prod : $quot )))) ;
         
         $cnt [31:0] = $reset ? 0 : >>1$cnt + 1 ;
                 
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
endmodule
```
##### In 2 cycle
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/0f44bdcc-d0e7-48d3-bd1f-0ff3b6117146)
##### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/a348dcd5-6a9d-4379-aa3d-bd8f1433ec32)
#### Code
```
\m4_TLV_version 1d: tl-x.org
\SV

   // =========================================
   // Welcome!  Try the tutorials via the menu.
   // =========================================

   // Default Makerchip TL-Verilog Code Template
   
   // Macro providing required top-level module definition, random
   // stimulus support, and Verilator config.
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   //$reset = *reset;
   
   |calc
      @0
         $reset = *reset;
         
      @1
         $val1 [31:0] = >>2$out [31:0];
         $val2 [31:0] = $rand2[3:0];
         
         $valid [31:0] = $reset ? 32'b0 : >>1$valid + 1 ;
         $valid_or_reset = $valid | $reset;
   
         
      ?$vaild_or_reset
         @1   
            $sum [31:0] = $val1 + $val2;
            $diff[31:0] = $val1 - $val2;
            $prod[31:0] = $val1 * $val2;
            $quot[31:0] = $val1 / $val2;
            
         @2                                           
            $out [31:0] = $reset ? 32'b0 : 
                          $valid_or_reset ? ($op[0] ? $sum : ($op[1] ? $diff : ($op[2] ? $prod : $quot ))) :
                          >>2$out;
            
                 
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule
```

#### Validity
##### Introduction to Validity and its Advantages
Validity is another feature in TL verilog, asserted if a particular transaction in a pipeline is valid or true. A new scope, called “when” scope, is introduced for this and is denoted as ?$valid. This new scope has many advantages - easier design, cleaner debugging, better error checking, and automated clock gating. The snapshot of validity introduced in the 2-cycle calculator is shown below.

The red lines show they don't care here. These are invalid signals.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ad51bd3f-ab1e-4c33-8344-69782160506c)

Clock gating is a power-saving feature. Use when we know the condition of the Flip-Flops is not required if the logic is not doing anything meaningful.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c18686f8-dfb9-49fa-a675-0357986f945b)

##### Validity and Valid When Condition
Using m4_TLV_version, we are enabling macro pre-processing. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b48416f9-f6dd-4b6f-b525-e8f813cd1ddc)
Macro Expands to: This is the System Verilog module definition expected by the Microchip Platform. This is asserted due to statement *passed = *cyc_cnt > 16'd30; if the cycle count exceeds 30. Here, we simulate for 30 cycles.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/6ea62899-436d-4aca-be3b-5c1053e0d386)
##### Distance Accumulator:  Pythagorean Theorem pipeline code
$tot_dist accumulates the running-total distance. Since it holds state, a reset value must be supplied. During reset ($reset asserted), the ‘0 leg of the mux is selected to reset $tot_dist to zero. $reset is assigned outside of the pipeline scope. This means it is assigned in stage 0 (@0) of a default (unspecified) pipeline. After reset, while there is no valid hop ($valid de-asserted), $tot_dist is retained by recirculating it through the mux. When there is a valid hop, the adder provides $tot_dist with $cc + $tot_dist.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3fa8d198-f267-4983-81a3-d3c381caf06b)
##### TL-Verilog vs. System Verilog Code
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/aff33e78-4b55-40f7-9bf5-41882b198ceb)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/febe31a1-4c31-4b82-847c-e9396a27b189)
##### Computing Total Distance
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/75a77031-695e-4f96-b493-75fc33114e97)
```
\m4_TLV_version 1d: tl-x.org
\SV
   `include "sqrt32.v";
   
   m4_makerchip_module
\TLV
   
   // Stimulus
   |calc
      @1
         $reset = *reset;
      ?$valid
         @1                                  // [>>>]
            $aa_sq[7:0] = $aa[3:0] ** 2;     // [>>>]
            $bb_sq[7:0] = $bb[3:0] ** 2;     // [>>>]
         @2                                  // [>>>]
            $cc_sq[8:0] = $aa_sq + $bb_sq;   // [>>>]
         @3                                  // [>>>]
            $cc[4:0] = sqrt($cc_sq);         // [>>>]
         @4
            $tot_dist[63:0] = 
                $reset ? '0 : 
                $valid ? >>1$tot_dist +$cc : 
                         >>1$tot_dist;
         
!   *passed = *cyc_cnt > 16'd30;
    
\SV
   endmodule

```

##### 2 Cycle Calculator with Validity
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/0fb07a00-3488-41e8-aa70-a644c16c3160)
#### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/638b8a49-83e9-4e96-93a6-34e6e98bd63a)
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/bd1f186fde018ff9e3fd80597b7397a1c862cf15/tlv_lib/calculator_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)

\TLV
   |calc
      @0
         $reset = *reset;
         $count = $reset ? 0 : >>1$count + 1;
         $valid = !($count);         
         $valid_or_reset = $valid || $reset;
         
      ?$valid_or_reset
         @1
            $val1[31:0] = $reset ? 0: >>2$out[31:0];
            $val2[31:0] = $rand2[3:0];

            $sum[31:0]  = $val1[31:0] + $val2[31:0];
            $diff[31:0] = $val1[31:0] - $val2[31:0];
            $prod[31:0] = $val1[31:0] * $val2[31:0];
            $quot[31:0] = $val1[31:0] / $val2[31:0];
            $oldop[2:0] = $op[2:0];

            //$count_num[31:0] = $reset ? 0 : >>1$count[31:0];
            //$count[31:0] = $count_num[31:0] + 1;

         @2
        
            $mem[31:0] = $reset ? 0 :
                          ($oldop[2:0] == 3'b101) ? $out:
                          $mem;
                          
            $out[31:0] = //($reset | !($count) ) ? 0 :
                         ($oldop[2:0] == 3'b000) ? $sum[31:0]:
                         ($oldop[2:0] == 3'b001) ? $diff[31:0]:
                         ($oldop[2:0] == 3'b010) ? $prod[31:0]:
                         ($oldop[2:0] == 3'b011) ? $quot[31:0]:
                         ($oldop[2:0] == 3'b100) ? >>1$mem:
                         $out;

      // Macro instantiations for calculator visualization(disabled by default).
      // Uncomment to enable visualisation, and also,
      // NOTE: If visualization is enabled, $op must be defined to the proper width using the expression below.
      //       (Any signals other than $rand1, $rand2 that are not explicitly assigned will result in strange errors.)
      //       You can, however, safely use these specific random signals as described in the videos:
      //o $rand1[3:0]
      //o $rand2[3:0]
      //o $op[3:0]
   m4+cal_viz(@3) // Arg: Pipeline stage represented by viz, should be atleast equal to last stage of CALCULATOR logic.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   

\SV
   endmodule
```

#### Single Value Memory
Here, we are adding the memory and recall operations. The mem is going to capture the value in the memory, and recall is going to bring it back to the main value in the calculator, which is the out signal.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/25d54385-2582-4670-b80f-f3787a50c7c4)

#### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/fbaf8c25-3b3a-42d0-8fb9-7df51e1d1303)
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/bd1f186fde018ff9e3fd80597b7397a1c862cf15/tlv_lib/calculator_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)

\TLV   
   |calc
      @0
         $reset = *reset;
         
      @1
         $val1 [31:0] = >>2$out;
         $val2 [31:0] = $rand2[3:0];
         
         $valid = $reset ? 1'b0 : >>1$valid + 1'b1 ;
         $valid_or_reset = $valid || $reset;
         
      ?$vaild_or_reset
         @1   
            $sum [31:0] = $val1 + $val2;
            $diff[31:0] = $val1 - $val2;
            $prod[31:0] = $val1 * $val2;
            $quot[31:0] = $val1 / $val2;
            
         @2   
            $mem[31:0] = $reset ? 32'b0 :
                         ($op[2:0] == 3'b101) ? $val1 : >>2$mem ;
            
            $out [31:0] = $reset ? 32'b0 :
                          ($op[2:0] == 3'b000) ? $sum :
                          ($op[2:0] == 3'b001) ? $diff :
                          ($op[2:0] == 3'b010) ? $prod :
                          ($op[2:0] == 3'b011) ? $quot :
                          ($op[2:0] == 3'b100) ? >>2$mem : >>2$out ;
            
            

      // Macro instantiations for calculator visualization(disabled by default).
      // Uncomment to enable visualisation, and also,
      // NOTE: If visualization is enabled, $op must be defined to the proper width using the expression below.
      //       (Any signals other than $rand1, $rand2 that are not explicitly assigned will result in strange errors.)
      //       You can, however, safely use these specific random signals as described in the videos:
      //  o $rand1[3:0]
      //  o $rand2[3:0]
      //  o $op[x:0]
      
   //m4+cal_viz(@3) // Arg: Pipeline stage represented by viz, should be atleast equal to last stage of CALCULATOR logic.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   

\SV
   endmodule
```

#### Hierarchy Example in TL-Verilog
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d28b7949-2826-44d0-97e6-d16a1ce07b1d)

## Basic RISC-V CPU micro-architecture
### Introduction to Simple RISC-V Micro-architecture
##### RISC-V Block Diagram
The program counter is a pointer to the instruction memory. So, the PC is sent into the instruction memory. Into the instruction, we execute next. The PC is sent to the instruction memory as an index. The data that comes back from the instruction memory is the instruction itself. The decoder is used to decode the instruction. The decoder picks the parts of the instruction register - the source register, the destination register, and instructions like branch instructions and immediate value. The branch instruction takes us from one instruction to target instruction based on the target.  

The MUX is used to compute the next PC for a branch instruction. The next PC for a branch is the incremented value of the PC with offset from the instruction applied. Rf and Rd are two port register files. So, we get two register values from Rf and Rd. from the register file and send them to ALU to perform arithmetic operations.  The result of the operation then returns to the memory. So, the register file also has the right port to write the result into the register file. 

In addition to that, we have loaded and stored memory instructions. The store instruction with the store address is provided relative to the register. The source register provides the base address, and effect is provided as an immediate field for the store instruction. These two are added together to provide the store address—the same thing for the load instruction, which will load from the memory. Load is going to access the memory and used to access the data. And it is also come back and written into the register file. 

The block diagram of a basic RISC-V microarchitecture is shown in the figure below. Now, using the Makerchip platform, the RISC-V microarchitecture or core is implemented. For starting the implementation, a starter code present here is used. The starter code consists of -

A simple RISC-V assembler.
An instruction memory containing the sum 1..9 test program.
Commented code for register file and memory.
Visualization.

The processor's design is based on three core steps: fetch, decode, and execute.

For each successive cycle, we are going to fetch a new instruction. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/67b96a01-9ab4-46a9-98a1-74029f75ba70)

#### Starting point Code for RISC-V
##### Implementation Plan
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ee1a4a84-8822-4f55-a9ce-3963d5e77e37)
##### Shell Code
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/579d6bf7-9df1-4b26-b855-fb83b6c1663a)
Link: https://github.com/stevehoover/RISC-V_MYTH_Workshop
##### Instructions in the memory
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/1aa6d087-afdf-42dd-bb24-864bb9f38693)

### Fetch and Decode
#### Implementation Plan for PC (Program Counter)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/5ceeed39-91b6-4d8f-a48d-535ac04e1d0b)
#### PC Logic
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b6c233e2-ed1b-4c9a-b058-9f33f424f338)
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/f54e4d0b-861f-478b-9006-ce7a56413a39)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //|cpu
      //m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
   
\SV
   endmodule
```

#### Fetch
During the fetch stage, processors fetch the instruction from the memory to the address pointed by the program counter. The program counters hold the address of the next stage; in our case, it is after 4 cycles, and the instruction memory holds the set of instructions to be executed. The snapshot of the fetch stage is shown below.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b20d4046-d4f6-46e3-8ecd-54df53b138d1)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/fb505f37-aa55-4e80-8fd1-492e315da6da)
#### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/62e9390d-a7c7-4c81-b4d6-73d8735b1842)
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |cpu
      m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)

\SV
   endmodule
```

#### Decode
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3a674de1-e764-48a5-9781-1dd15ef92ea5)
For decoding a particular instruction, it is necessary that the instruction type and format are known to the processor. To avoid errors, the decoding must be done properly according to the given format. There are 6 instruction types in RISC-V :

#### Instruction Type Decode
The lower 2 bits, bits 0 and 1, are always 1 for the base instruction set. We are going to ignore those 2 bits. So we are decoding the bits 6:2.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/7bba07b0-60e8-4443-a48f-acc5aeaafd7b)

Register (R) type
Immediate (I) type
Store (S) type
Branch (B) type
Upper immediate (U) type
Jump (J) type
Following decoding the above, the instruction immediately decodes for all the above, except the register type is added. The 6 other instruction format/fields, including the opcode, 2 source register, destination register, and funct3 and funct7 decode, is included. Next, the instruction field decode of the different instruction types is inserted to ensure that only valid registers are used. Finally, the base instruction set decode for the various fields is incorporated. The instruction type and format are shown in the figure below and are sourced from here.

#### Instruction Immediate Decode
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/7c93fb6f-d82a-4ecc-ae1c-b583afefc26f)
#### Ectract other instruction fields
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/46c1de3b-f585-417d-a55f-2a0e62cf0ca0)
#### Using when conditions
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/35a08c6a-1243-4b80-b950-b362cebaca86)
#### RV32I Base Instruction: Decode Individual Instructions
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d0c9d5d2-953a-4b43-a59c-d83a11de2f80)

### Instruction Decode
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/aface58f-5f45-4d4f-b2e0-7bf655924a8a)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $funct3[3:0] = $instr[14:12];
   
         $opcode[6:0] = $instr[6:0];
         
         $funct7_valid = $is_r_instr;
         ?$rs2_valid
            $funct7[6:0] = $instr[31:25];
            
         $dec_bits[10:0] = {$funct[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits == 11'b0_000_0110011;

     
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |cpu
      m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
   
\SV
   endmodule
```

### RISC-V Control Logic
Here the Register file is 2 reads, 1 write, which means 2 read and 1 write operations can happen simultaneously.

Inputs:

Read_Enable - Enable signal to perform a read operation
Read_Address1 - Address1 from where data has to be read
Read_Address2 - Address2 from where data has to be read
Write_Enable - Enable signal to perform write operation
Write_Address - Address where data has to be written
Write_Data - Data to be written at Write_Address
Outputs:

Read_Data1 - Data from Read_Address1
Read_Data2 - Data from Read_Address2
Below is a snapshot from Makerchip IDE after performing the Register File Read followed by Register File Write.

#### Register File Read (UPDATED SHELL CODE)
The fields we decoded tell us what the source register instruction is and use that to control the Read Register File.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/525624bf-a0fc-4723-8dc7-fb47c58d940f)
The destination register in RISC-V is called rd. This is the destination register that we are writing. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/31130c8c-5568-4553-bf3f-3d41816fa107)

#### Register File Read Lab
src1 and src2 validate the signals coming out of the file.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/de297b5b-08ee-4e4a-b24b-31c954c66b89)

#### ALU Operations for add/ addi
Here, the ALU produces an output called $result[31:0]. The instructions we need add, addi, and blt (Branch less than doesn't produce a valid destination. So we need to assign this a result value).
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/a51b7d7d-4150-47e9-aa74-ae537a0829c0)
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/aff22f5d-de94-47ee-a240-4b51a2fd3927)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         
         //NEXT PC
         $pc[31:0] = >>1$reset ? 32'b0 : >>1$pc + 32'd4;
         
         //INSTRUCTION FETCH
      @1
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $imem_rd_en = !$reset;
         $instr[31:0] = $imem_rd_data[31:0];
         
         
         //INSTRUCTION TYPES DECODE         
      @1
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         //INSTRUCTION IMMEDIATE DECODE
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         
         
         //INSTRUCTION DECODE
         $opcode[6:0] = $instr[6:0];
         
         
         //INSTRUCTION FIELD DECODE
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
         
         
         //INSTRUCTION DECODE
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         
         `BOGUS_USE ($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
         
         
         //REGISTER FILE READ
         $rf_wr_en = 1'b0;
         $rf_wr_index[4:0] = 5'b0;
         $rf_wr_data[31:0] = 32'b0;
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;
         
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
         
         //ARITHMETIC AND LOGIC UNIT (ALU)
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;
         
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
   
   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic
                       // @4 would work for all labs
\SV
   endmodule
```

#### Register File Read
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b9f11326-2b11-41f6-96a3-b90cd2e4520c)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/4dcec20e-8159-48ee-bd3f-747716d3c1ae)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $funct3[3:0] = $instr[14:12];
   
         $opcode[6:0] = $instr[6:0];
         
         $funct7_valid = $is_r_instr;
         ?$rs2_valid
            $funct7[6:0] = $instr[31:25];
            
         $dec_bits[10:0] = {$funct[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits == 11'b0_000_0110011;
         
         $rf_rd_en1 = !$rs1_valid;
         $rd_rd_en2 = !$rs2_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_index2[4:0] = $rs2;
         $rf_rd_data1[31:0] = $src1_value[31:0]; 
         $rf_rd_data2[31:0] = $src2_value[31:0];
         
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
   
\SV
   endmodule
```

#### Register File Write
Here rd is for the destination register. We read when the destination register is valid.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ccfd89ae-2674-4ff7-a430-ac26945c2382)
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/a4c6eb3e-461d-422b-be8e-207b8ea1a050)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/0226e655-a3e8-4843-a093-42e3cad9c7bc)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $funct3[3:0] = $instr[14:12];
   
         $opcode[6:0] = $instr[6:0];
         
         $funct7_valid = $is_r_instr;
         ?$rs2_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_u_instr || $is_j_instr || $is_i_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7]; 
            
         $dec_bits[10:0] = {$funct[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits == 11'b0_000_0110011;
         
         `BOGUS_USE($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
         
         $rf_rd_en1 = $rs1_valid;
         $rd_rd_en2 = $rs2_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_index2[4:0] = $rs2;
         $rf_rd_data1[31:0] = $src1_value[31:0]; 
         $rf_rd_data2[31:0] = $src2_value[31:0];
         
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx;
         
         $rf_wr_en = ($rd_valid || $rd !== 5'b0);  
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $result;
         
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
 
\SV
   endmodule
```

#### Arrays - What's inside?
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/47127d3a-da72-4980-8ab2-38e971977193)
#### Register File Write and Read
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/51899dd8-5ce6-48ab-8b2f-34aad58909c3)

#### Implementing Branch Instructions
Here B, type instructions are branch instructions
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c98354ff-fc4d-47db-92f4-d6860161c332)
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/36feed27-b86d-4cc9-a4a3-50028efb03bf)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         
         //NEXT PC
         $pc[31:0] = >>1$reset ? 32'b0 : >>1$pc + 32'd4;
         
         //INSTRUCTION FETCH
      @1
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $imem_rd_en = !$reset;
         $instr[31:0] = $imem_rd_data[31:0];
         
         
         //INSTRUCTION TYPES DECODE         
      @1
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         //INSTRUCTION IMMEDIATE DECODE
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         
         
         //INSTRUCTION DECODE
         $opcode[6:0] = $instr[6:0];
         
         
         //INSTRUCTION FIELD DECODE
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
         
         
         //INSTRUCTION DECODE
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         
         `BOGUS_USE ($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
         
         
         //REGISTER FILE READ         
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;
         
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
         
         //ARITHMETIC AND LOGIC UNIT (ALU)
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;
         
         //REGISTER FILE WRITE
         $rf_wr_en = $rd_valid && $rd != 5'b0;
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $result;
         
         //BRANCH INSTRUCTIONS
         $taken_branch = $is_beq ? ($src1_value == $src2_value):
                         $is_bne ? ($src1_value != $src2_value):
                         $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bltu ? ($src1_value < $src2_value):
                         $is_bgeu ? ($src1_value >= $src2_value):
                                    1'b0;
         `BOGUS_USE($taken_branch)
         
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
   
   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic
                       // @4 would work for all labs
\SV
   endmodule
```

#### Where we need to Branch to:
This branch can be a forward or backward branch. If the previous instruction is taken then we select the PC: branch_target_PC. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c01e8f7e-5440-47d5-a2d1-dc2ffc1cb02a)

#### Completing Branch Instruction Implementation
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/f5c8572d-869d-4638-b310-a18dc3e062bb)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         
         //MODIFIED NEXT PC LOGIC FOR INCLUDING BRANCH INSTRCUTIONS
         $pc[31:0] = >>1$reset ? 32'b0 :
                     >>1$taken_branch ? >>1$br_target_pc :
                     >>1$pc + 32'd4;
         
         //INSTRUCTION FETCH
      @1
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $imem_rd_en = !$reset;
         $instr[31:0] = $imem_rd_data[31:0];
         
         
         //INSTRUCTION TYPES DECODE         
      @1
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         //INSTRUCTION IMMEDIATE DECODE
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         
         
         //INSTRUCTION DECODE
         $opcode[6:0] = $instr[6:0];
         
         
         //INSTRUCTION FIELD DECODE
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
         
         
         //INSTRUCTION DECODE
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         
         `BOGUS_USE ($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
         
         
         //REGISTER FILE READ         
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;
         
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
         
         //ARITHMETIC AND LOGIC UNIT (ALU)
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;
         
         //REGISTER FILE WRITE
         $rf_wr_en = $rd_valid && $rd != 5'b0;
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $result;
         
         //BRANCH INSTRUCTIONS 1
         $taken_branch = $is_beq ? ($src1_value == $src2_value):
                         $is_bne ? ($src1_value != $src2_value):
                         $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bltu ? ($src1_value < $src2_value):
                         $is_bgeu ? ($src1_value >= $src2_value):
                                    1'b0;
         `BOGUS_USE($taken_branch)
         
         //BRANCH INSTRUCTIONS 2
         $br_target_pc[31:0] = $pc +$imm;
         
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
   
   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic
                       // @4 would work for all labs
\SV
   endmodule
```

#### Simple Testbench
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/282cc912-aeee-4ba9-8474-984afef7dead)
### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/48a827bf-2d90-40b2-94ce-805231bc3ef8)
### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
         $reset = *reset;
         
         //MODIFIED NEXT PC LOGIC FOR INCLUDING BRANCH INSTRCUTIONS
         $pc[31:0] = >>1$reset ? 32'b0 :
                     >>1$taken_branch ? >>1$br_target_pc :
                     >>1$pc + 32'd4;
         
         //INSTRUCTION FETCH
      @1
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $imem_rd_en = !$reset;
         $instr[31:0] = $imem_rd_data[31:0];
         
         
         //INSTRUCTION TYPES DECODE         
      @1
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         //INSTRUCTION IMMEDIATE DECODE
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         
         
         //INSTRUCTION DECODE
         $opcode[6:0] = $instr[6:0];
         
         
         //INSTRUCTION FIELD DECODE
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
         
         
         //INSTRUCTION DECODE
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         
         `BOGUS_USE ($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
         
         
         //REGISTER FILE READ         
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;
         
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
         
         //ARITHMETIC AND LOGIC UNIT (ALU)
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;
         
         //REGISTER FILE WRITE
         $rf_wr_en = $rd_valid && $rd != 5'b0;
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $result;
         
         //BRANCH INSTRUCTIONS 1
         $taken_branch = $is_beq ? ($src1_value == $src2_value):
                         $is_bne ? ($src1_value != $src2_value):
                         $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bltu ? ($src1_value < $src2_value):
                         $is_bgeu ? ($src1_value >= $src2_value):
                                    1'b0;
         `BOGUS_USE($taken_branch)
         
         //BRANCH INSTRUCTIONS 2
         $br_target_pc[31:0] = $pc +$imm;
         
         
         //TESTBENCH
          *passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9) ;
         
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
   
   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic
                       // @4 would work for all labs
\SV
   endmodule
```

### Pipelined RISC-V CPU micro-architecture
#### Introduction to Control Flow Hazard and Read after Write Hazard
Now, pipelining of the CPU core is done, which allows easy retiming and reduces functional bugs to a great extent. Pipelining allows faster computation. For pipelining, as mentioned earlier, we need to add @1, @2, and so on. The snapshot of the pipelining is shown below. In TL verilog, another advantage is that defining the pipeline in systematic order is unnecessary. More information on timing abstract can be found in the IEEE paper "Timing-Abstract Circuit Design in Transaction-Level Verilog" by Steeve Hoover in Makerchip platform itself.

Converting non-pipelined CPU to pipelined CPU using timing abstract feature of TL-Verilog. This allows easy retiming without any risk of functional bugs. More details regarding Timing Abstract in TL-Verilog can be found in IEEE Paper "Timing-Abstract Circuit Design in Transaction-Level Verilog" by Steven Hoover.

Pipelining the CPU with branches still having 3 cycle delay; rest all instructions are pipelined. Pipelining the CPU in TL-Verilog can be done in the following manner:

```
|<pipe-name>
    @<pipe stage>
       Instructions present in this stage
       
    @<pipe_stage>
       Instructions present in this stage       
```

Test case:

```
*passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9);
```
Similar to the branch, the load will also have 3 3-cycle delays. So, I added a Data Memory 1 write/read memory.


Inputs:
Read_Enable - Enable signal to perform a read operation
Write_Enable - Enable signal to perform write operation
Address - Address specified whether to read/write from
Write_Data - Data to be written on Address (Store Instruction)
Output:

Read_Data - Data to be read from Address (Load Instruction)
Added test case to check the functionality of load/store. Stored the summation of 1 to 9 on address 4 of Data Memory and loaded that value from Data Memory to r17.

```
*passed = |cpu/xreg[17]>>5$value == (1+2+3+4+5+6+7+8+9);
```

### Completing the RISC-V CPU
Added Jumps and completed Instruction Decode and ALU for all RV32I base integer instruction set instructions.

### Output
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3ee6e141-144a-4f93-9929-43184307236c)

### Code
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

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
   m4_asm(SW, r0, r10,100)
   m4_asm(LW, r15, r0,100)
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         //Program Counter
         $reset = *reset;
         $pc[31:0] = >>3$valid_taken_br ? >>3$br_tgt_pc :
                     >>3$valid_load ? >>3$pc + 32'd4 :
                     (>>3$is_jal && >>3$valid) ? >>3$br_tgt_pc :
                     (>>3$is_jalr && >>3$valid)? >>3$jalr_tgt_pc:
                     >>1$reset ? 0 :
                     >>1$pc + 32'd4;
         
         //$start = !$reset && >>1$reset;
         //$valid = $reset ? 1'b0 : ($start ? 1'b1 : >>3$valid);
         
      @1
         //Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0];
         
         //types of instructions
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         //Decoding Instruction Immediate Type using concatenation
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         //Assigning when statements
         $funct7_valid = $is_r_instr;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$funct3_valid
            $funct3[3:0] = $instr[14:12];
            
         $rd_valid = $is_r_instr || $is_u_instr || $is_j_instr || $is_i_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
            
         $opcode_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr || $is_u_instr || $is_j_instr ;
         ?$opcode_valid
            $opcode[6:0] = $instr[6:0];
            
      @2   
         //Decoding individual instructions
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         
         $is_lui = $dec_bits ==? 11'bx_xxx_0110111;
         $is_auipc = $dec_bits ==? 11'bx_xxx_0010111;
         $is_jal = $dec_bits ==? 11'bx_xxx_1101111;
         $is_jalr = $dec_bits ==? 11'bx_000_1100111;
         $is_load = $dec_bits ==? 11'bx_xxx_0000011;
         $is_store = $dec_bits ==? 11'bx_0xx_0100011;
         //$is_sh = $dec_bits ==? 11'bx_001_0100011;
         //$is_sw = $dec_bits ==? 11'bx_010_0100011;
         $is_slti = $dec_bits ==? 11'bx_010_0010011;
         $is_sltiu = $dec_bits ==? 11'bx_011_0010011;
         $is_xori = $dec_bits ==? 11'bx_100_0100011;
         $is_ori = $dec_bits ==? 11'bx_110_0100011;
         $is_andi = $dec_bits ==? 11'bx_111_0100011;
         $is_slli = $dec_bits ==? 11'b0_001_0100011;
         $is_srli = $dec_bits ==? 11'b0_101_0100011;
         $is_srai = $dec_bits ==? 11'b1_101_0100011;
         $is_sub = $dec_bits ==? 11'b1_000_0110011;
         $is_sll = $dec_bits ==? 11'b0_001_0110011;
         $is_slt = $dec_bits ==? 11'b0_010_0110011;
         $is_sltu = $dec_bits ==? 11'b0_011_0110011;
         $is_xor = $dec_bits ==? 11'b0_100_0110011;
         $is_srl = $dec_bits ==? 11'b0_101_0110011;
         $is_sra = $dec_bits ==? 11'b1_101_0110011;
         $is_or = $dec_bits ==? 11'b0_110_0110011;
         $is_and = $dec_bits ==? 11'b0_111_0110011;
         
         //System Verilog Macro
         `BOGUS_USE ($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
         
         //Register File Read
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;
         
         $src1_value[31:0] = ((>>1$rf_wr_en) && (>>1$rd == $rs1)) ? >>1$result : $rf_rd_data1;
         $src2_value[31:0] = ((>>1$rf_wr_en) && (>>1$rd == $rs2)) ? >>1$result : $rf_rd_data2;
         
      @3   
         //ALU
         
         $sltu_rslt = ($src1_value <  $src2_value) ;
         $sltiu_rslt =  ($src1_value < $imm );
         
         $result[31:0] = $is_addi ? ($src1_value + $imm) :
                         $is_add  ? $src1_value + $src2_value :
                         $is_andi ? $src1_value & $imm :
                         $is_ori ? $src1_value | $imm :
                         $is_xori ? $src1_value ^ $imm :
                         $is_slli ? $src1_value << $imm[5:0] :
                         $is_srli ? $src1_value >> $imm[5:0] :
                         $is_and ? $src1_value & $src2_value :
                         $is_or ? $src1_value | $src2_value :
                         $is_xor ? $src1_value ^ $src2_value :
                         $is_sub  ? $src1_value - $src2_value :
                         $is_sltu ? $src1_value < $src2_value :
                         $is_sltiu ? $src1_value < $imm :
                         $is_sll ? $src1_value << $src2_value[4:0] :
                         $is_srl ? $src1_value >> $src2_value[4:0] :
                         $is_lui ? {$imm[31:12],12'b0} :
                         $is_auipc ? $imm + $pc :
                         $is_jal ? $pc + 32'd4 :
                         $is_jalr ? $pc + 32'd4 :
                         $is_load ? $src1_value + $imm :
                         $is_store ? $src1_value + $imm :
                         $is_srai ? { {32{$src1_value[31]}}, $src1_value} >> $imm[4:0] :
                         $is_sra ? { {32{$src1_value[31]}}, $src1_value} >> $src2_value[4:0] :
                         $is_slt ? (($src1_value[31] == $src2_value[31]) ? $sltu_rslt : {31'b0,$src1_value[31]} ) :
                         $is_slti ? (($src1_value[31] == $imm[31]) ? $sltiu_rslt : {31'b0,$src1_value[31]} ) : 32'bx ;
         
         
         //Register File Write (avoiding invalid write instructions)
         $rf_wr_en = ($rd_valid) && ($rd != 5'b0) && ($valid) || (>>2$valid_load);
         $rf_wr_index[4:0] = >>2$valid_load ? >>2$rd : $rd;
         $rf_wr_data[31:0] = >>2$valid_load ? >>2$ld_data: $result;
         
         
         
         //Branching
         $beq = ($src1_value == $src2_value ) ? 1'b1 :1'b0 ;
         $bne = ($src1_value != $src2_value ) ? 1'b1 :1'b0 ;
         $bltu = ($src1_value < $src2_value ) ? 1'b1 :1'b0 ;
         $bgeu = ($src1_value >= $src2_value ) ? 1'b1 :1'b0 ;
         $blt = ( ($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31] )) ? 1'b1 : 1'b0 ;
         $bge = ( ($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31] )) ? 1'b1 : 1'b0 ;
         
         $taken_br = ( ($is_beq && $beq) || ($is_bne && $bne) ||
                       ($is_blt && $blt) || ($is_bge && $bge) ||
                       ($is_bltu && $bltu) || ($is_bgeu && $bgeu) ) ? 1'b1 :1'b0 ;
         
         //Jump
         $is_jump = $is_jal || $is_jalr;
         $jalr_tgt_pc[31:0] = $src1_value + $imm;
         
         //Signal Validation
         $valid_taken_br = $valid && $taken_br;
         $valid_load = $is_load && $valid;
         $valid_jump = $is_jump && $valid;
         $valid = !((>>1$valid_taken_br || >>2$valid_taken_br) || (>>1$valid_load || >>2$valid_load) || ($valid_jump));
         
         $br_tgt_pc[31:0] = $pc + $imm;
         
         *passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9);
         
      @4
         $dmem_wr_en = ($is_s_instr) && ($valid);
         $dmem_addr[3:0] = $result[5:2];
         $dmem_wr_data[31:0] = $src2_value;
         $dmem_rd_en = ($is_load) && ($valid);
         
      @5
         $ld_data[31:0] = $dmem_rd_data;
         
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
```

### Conclusion
This project was part of the RISC-V-based MYTH (Microprocessor for You in Thirty Hours) workshop conducted by Kunal Ghosh and Steve Hoover. The current project implements almost the entire RV32I base instruction set. We can execute all RISC-V instructions in four cycles with easy pipelining using Transaction-Level Verilog. TL-Verilog reduces your code size significantly and allows us to freely declare signals without explicitly declaring them (just like Python does compared to C). In addition, we can generate Verilog/SystemVerilog code from TL-Verilog in Makerchip IDE using the Sandpiper compiler.




























































