# RISC-V_ISA

#### Introduction to RISC-V Basics
##### RISC-V Instruction Set Architecture
This is the way we are going to talk to the computers. Suppose we need a C program to run on a computer/ hardware with a particular layout (interior of the chip present inside the laptop). The C program is first compiled into assembly program language, which is nothing but the RISC-V assembly language program. This assembly language program is converted into the machine language program in the form of a binary language program, which is understood by the hardware of the computer present in the hexadecimal format. 

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/03e27285-21d4-4cc2-9e6e-59d8737b10c5) </br>

We need to implement the RISC-V specification present in C language into some RTL. From RTL to layout, it is called the standard PnR flow (RTL to GDS flow). The entire flow starts from the RISC-V architecture. And implemented in RTL and RTL to the layout.

##### From Applications to Hardware

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c8ad70e5-8717-4b0d-a4df-2c55a4524b0f) </br>

The system software converts the application software into binary language to be executed on the hardware. The major components of the system software are the OS, compiler, and assembler. The compiler converses the respective C programming language code into the particular instruction set architecture with respect to the hardware. Thus, the output of the compiler is dependent on the hardware. This is in .exe format. The assembler's job is to take the instructions and convert them into the binary format. Basically, it is called a machine language program. The hardware generates the outputs according to the machine language program input, which is in the form of binary numbers. 

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/35cc4f60-4d35-4342-92c9-37517bf18b57) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/175a5d1d-b648-4562-88d4-1e3ccc60af58) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3fe721ff-3bce-4213-94e1-907ae51680c7) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/74580d17-1b12-4a51-9b05-fc210fa6af70) </br>

The instruction acts as the abstract interface between the C program and the hardware. This is called the Instruction Set Architecture or called the Architecture of the computer. The hardware only understands only 1’s and 0’s as inputs. We need a Hardware Description Language that implements particular specifications. This is called the RTL implementation of the specifications. The RTL here is synthesized into the netlist. Then, we do the Physical Design implementation of the Synthesized netlist of the RTL.  

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e1f8f06a-e73c-4ac7-9ee2-60aafd9264cf) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/47943449-4885-4ae9-813c-ae987c37c47e) </br>

#### Basics
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

#### Labwork for RISC-V
##### C Program to Compute Sum From 1 to N
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/56542919-b5e8-4511-8cbf-be2a96113877)
Output:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/947c4cce-b940-4dd1-861a-5eb529815054)

##### RISCV GCC Compile and Disassemble
Compiling the same code with RISC-V gcc compiler:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/9226d880-fc09-45a7-bc17-f7c950b112c1)

Assembly code for which we are trying to run the C program:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/2e12d157-75e9-4c2b-8a66-07bfc22dc0fe)

15 instructions came out when we the options -o1 and other options.
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c043ad04-be08-405e-ab40-fa659aba1135)

Running the command with different options:
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/54a05cf8-a28a-4a9f-b426-22a33e0194c4)

##### Spike Simulation and Debug
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

#### Integer number representation
##### 64-bit Number System for Unsigned Numbers
There has to be an interface that converts humans' understanding of decimal format to computers' understanding of binary format. 
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/dda3db1c-d95c-4556-a604-8539e43a8ce9)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/d8869fb2-c2ba-4936-bc21-2ad9ce16338f)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/f09e0e73-abea-435b-8ae5-8eee4fc47186)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/2c1a269d-64d6-4013-a386-9eccb65b2a2a)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/7d6058be-2494-4b94-a4cd-17f5a634c3c6)
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3407b46a-448c-4d49-b6d7-474c497cdede)

##### 64-bit Number System for Signed Numbers
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

























































