# lecture 1 :- How to Talk to Computers

## Introduction to QFN-48 Package, Chip, Pads, Core, die, and IPs

The Below Image is FGPA Board or ARDUINO Board

<img width="527" alt="Screenshot 2024-08-04 at 2 23 48 PM" src="https://github.com/user-attachments/assets/5321a2c2-05c7-4972-956a-75ea05e766b8">

source :- VLSI System Design

In this We will be Learning about the CHIP (Processor/SoC)

A processor consists of the All The Informations Like
1. RAMS
2. Power and Ground ports
3. Communication interface
4. Jtag Interface etc..,

<img width="977" alt="Screenshot 2024-08-04 at 2 24 56 PM" src="https://github.com/user-attachments/assets/3d9e49c1-af5d-4143-9a2c-56a36a6645ee">

source :- VLSI System Design

After we open Up an IC also known a Package

<img width="875" alt="Screenshot 2024-08-04 at 2 27 03 PM" src="https://github.com/user-attachments/assets/7bb15996-4c85-4b46-a2dd-6fb49b798170">
source :- VLSI System Design


The chip will be Integrated in Middle of The Package
 
 <img width="635" alt="Screenshot 2024-08-04 at 2 27 45 PM" src="https://github.com/user-attachments/assets/34c73871-1a23-4e85-9f56-f911cb0dd434">

 source:- VLSI System Design


The Chip has the Various Components Like 
1. Pads
Here basically Communication from outside to inside of the chips happens

<img width="651" alt="Screenshot 2024-08-04 at 2 30 28 PM" src="https://github.com/user-attachments/assets/fedb36bf-7b66-4104-9288-6d459f751e04">

source :- VLSI System Design

2. Core and Die
<img width="480" alt="Screenshot 2024-08-04 at 2 32 16 PM" src="https://github.com/user-attachments/assets/409b38d7-c109-4921-8ef1-f881686c582a">

source :- https://www.vlsisystemdesign.com/kunal58625/php/physical_design_forum.php

Example SoC :- 
RISCV Soc


<img width="597" alt="Screenshot 2024-08-04 at 2 33 52 PM" src="https://github.com/user-attachments/assets/e01ea8e0-cd3b-4fce-a61a-210d2851f133">

source :- VLSI System Design

From image we can see various Ip's which will be given by Foundary IP



## Introduction to RISC-V

RISC-V Instruction Set Architecture (ISA)

This a top level View of how we talk to the computer Through Set of Instructions or Assembly Language Program,
and is converted into Binary level Operations


## From Software Application to Hardware

Q1. Important question we are gona answer is How is Software application is run on an Hardware ??

Application Software --> System Software --> Hardware

                                          --------------      --------------------
Prgramming Language (c, c++,java etc) --> | COMPILER   | -->  | Instruction sets |  --> .exe File
                                          --------------      --------------------
                                          
Now executable File is run into assembler and Converted to Binary

Eg:- 

<img width="1129" alt="Screenshot 2024-08-04 at 2 47 53 PM" src="https://github.com/user-attachments/assets/64f2b04e-f409-4e7b-bb34-1ad6f4e66253">

source :-  VLSI System Design

