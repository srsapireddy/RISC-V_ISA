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
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/389d9d75-36ab-4780-a8e8-ed2d459da5a6)
Makerchip link: https://makerchip.com/
Pipelined FPGA Multiplier Example:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d60eed37-63dd-4332-9e96-4b6ae75e30d3)
Link: https://makerchip.com/sandbox/00Rf2hDnr/0lOh4v

#### Labs for Combinational Logic
Exercise 1:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ada93032-494a-419f-af8e-6cfe2fdfcf3d)
Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/ba5a18dd-4acf-438a-8be4-ace026c60625)

Exercise 2:
Initially, we started understanding the Makerchip IDE platform by trying some basic digital logic gates, with the inverter being the standard. In TL Verilog, we code the logic itself viz $out =!$in1 without declaring the variables separately, and $in an assignment is also not required. The output of the above is shown in the figure below. We note that simultaneous highlighting of the variable is possible at the output.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3292720d-199d-408a-b684-8d016b2f9cd7)
Output:
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

Exercise 3: Vectors Lab
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/12fc1968-69da-4270-9b8b-d6828ea32e5d)
Output:
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

Exercise 4: Mux
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/32e70599-7e5c-4b5a-aaf5-6ebecc0f435c)
Output 1:
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
Output 2:
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


Exercise 5: Combinational Calculator
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/b30398ac-9296-470c-a6d3-bab0aeccb9a8)
Output:
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







































































