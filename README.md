# RISC-V_ISA

#### Introduction to RISC-V Basics
##### RISC-V Instruction Set Architecture
This is the way we are going to talk to the computers. If we need a C program to run on computer/ hardware with a particular layout (interior of the chip present inside the laptop). The C program is first compiled into assembly program language which is nothing but the RISC-V assembly language program. This assembly language program is converted into the machine language program in the form of binary language program which is understood by the hardware of the computer present in the hexadecimal format. 

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/03e27285-21d4-4cc2-9e6e-59d8737b10c5) </br>

We need to implement the RISC-V specification present in C language into some RTL. From RTL to layout is called as the standard PnR flow (RTL to GDS flow). The entire flow starts from the RISC-V architecture. And implemented in RTL and RTL to layout.

##### From Applications to Hardware

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/c8ad70e5-8717-4b0d-a4df-2c55a4524b0f) </br>

The system software converts the application software into binary language to be executed on the hardware. The major components of the system software are the OS, compiler and the assembler. The compiler convers the respective C programming language code into the particular instruction set architecture with respect to the hardware. Thus, the output of the compiler is dependent on the hardware. This is in .exe format. The job of the assembler is to take the instructions and convert it into the binary format. Basically, called as a machine language program. And the hardware generates the outputs according to the machine language program input which is in the form of binary numbers. 

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/35cc4f60-4d35-4342-92c9-37517bf18b57) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/175a5d1d-b648-4562-88d4-1e3ccc60af58) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/3fe721ff-3bce-4213-94e1-907ae51680c7) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/74580d17-1b12-4a51-9b05-fc210fa6af70) </br>

The instruction acts as the abstract interface between the C program and the hardware. This called as the Instruction Set Architecture or called the Architecture of the computer. The hardware only understands only 1’s and 0’s as inputs. We need an Hardware Description Language which implements particular specifications. This is called as the RTL implementation of the specifications. The RTL here is synthesized into the netlist. Then we do the Physical Design implementation of the Synthesized netlist of the RTL.  

![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/e1f8f06a-e73c-4ac7-9ee2-60aafd9264cf) </br>
![image](https://github.com/srsapireddy/RISC-V_ISA/assets/32967087/47943449-4885-4ae9-813c-ae987c37c47e) </br>


