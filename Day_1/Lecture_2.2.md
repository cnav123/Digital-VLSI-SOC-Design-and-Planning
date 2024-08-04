## Simplified RTL2GDS flow

<img width="759" alt="Screenshot 2024-08-04 at 2 58 50 PM" src="https://github.com/user-attachments/assets/1862de8a-3b66-40e0-b5f6-fac1b353f458">

source :- VLSI System Design


1. Synthesis

In this Stage we convert RTL to a circuit components from the standard cell Library (SCL)


2. Floor/Power Planning

Floor plan : Partion the chip die between diferent system building blocks and place the I/O Pads

<img width="446" alt="Screenshot 2024-08-04 at 3 03 20 PM" src="https://github.com/user-attachments/assets/e8f19d7c-ef15-41ca-a3a1-b3b847a37969">

source :- VLSI System Design

Power Plan : Here we will assign the VDD and VSS Power pads to the design

<img width="296" alt="Screenshot 2024-08-04 at 3 04 23 PM" src="https://github.com/user-attachments/assets/58be0310-0b24-4a10-acbe-00ee57663a81">

source :- VLSI System Design


3. Placement

Place the cells on the floorplan rows, sligned with the sites

<img width="392" alt="Screenshot 2024-08-04 at 3 05 25 PM" src="https://github.com/user-attachments/assets/34e3c9c7-4364-4356-ad59-d06c0da49351">


source :- VLSI System Design


4. Clock Tree Synthesis (CTS)

CTS is mainly performed so that all the sequential flops recieve the clock at the same time

![image](https://github.com/user-attachments/assets/cf31ee38-bd8f-410a-8412-07bdbe905b5e)

source :- https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.semanticscholar.org%2Fpaper%2FClock-Tree-Synthesis-for-Timing-Convergence-and-in-Tsai%2Fa4a3081cd4cf75587dcf37fe62f39338a24235dc&psig=AOvVaw23hCWsul24wTHohQs8030H&ust=1722850615396000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCKCikeqE24cDFQAAAAAdAAAAABAE


5. Routing

Implement the interconnect using ythe available metal Layers

<img width="184" alt="Screenshot 2024-08-04 at 3 07 58 PM" src="https://github.com/user-attachments/assets/87b1cc62-ba19-4c7b-b202-71e10ad359b4">

source :- VLSI System Design


6. Sign Off

Physical Verifications
  1. Design Rules Checking (DRC)
  2. Layout vs. Schematic (LVS)

Timing Verification 
  1. Static timing Analysis

Output we will get as GDSII File (Graphical Data Stream)
