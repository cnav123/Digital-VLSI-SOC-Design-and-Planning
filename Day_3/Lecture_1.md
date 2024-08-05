# Lecture 1 :- Labs For CMOS Inverter ngspice simulations

1. SPICE deck creation for CMOS Inverter

2. SPICE SImulation LAB for CMOS Inverter

3. Switching Threshold Vm

4. Static and Dynamic Simulation of CMOS Inverter

5. Labs steps to git clone vsdstdcelldesign


## SPICE Deck reation for CMOS Inverter

Voltage Threshold Charecteristics

Spice deck :- is Information of Components used and their connectivity which is used

1. Component Connectivity

2. Component values

Example :- 

<img width="260" alt="Screenshot 2024-08-04 at 9 58 53 PM" src="https://github.com/user-attachments/assets/16df4528-4c12-4ddf-911d-673e4e6761b2">

source :- VLSI System Design


3. Identify the Nodes

<img width="656" alt="Screenshot 2024-08-04 at 9 59 26 PM" src="https://github.com/user-attachments/assets/09cdbdc3-641e-406c-baae-3e3391f75b3f">

source :- VLSI System Design


4. Name Nodes :-

<img width="491" alt="Screenshot 2024-08-04 at 10 00 16 PM" src="https://github.com/user-attachments/assets/7f765cf2-4e56-4137-8e1b-6b2dc50308fc">

source :- VLSI System Design


Here is the Example file

```
*** MODEL DESCRIPTION ***
*** NETLIST DESCRIPTION ***
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u L=0.25u

cload out 0 10f

Vdd vdd 0 2.5
Vin in 0 2.5

*** SIMULATION Commands***
.op
.dc Vin 0 2.5 0.05

*** .include tsmc_025um_model.mod ***
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```

### SPICE waveform : Wn/Ln = Wp/Lp = 1.5 same

Here is the output we get

<img width="911" alt="Screenshot 2024-08-04 at 10 05 58 PM" src="https://github.com/user-attachments/assets/7c77a966-cbc8-4a06-a0f5-6e72c875e15d">

source :- VLSI System Design


Now for the case where the w/l is different for pmos and nmos

### SPICE waveform : Wn/Ln =  1.5, Wp/Lp = 2.5 (PMOS is wider)

<img width="383" alt="Screenshot 2024-08-04 at 10 07 52 PM" src="https://github.com/user-attachments/assets/cf6e821f-c9bc-4982-9672-a7003373a01d">



## Switching Threshold Vm

<img width="1155" alt="Screenshot 2024-08-05 at 7 01 54 AM" src="https://github.com/user-attachments/assets/26528759-9c70-4dbb-bc07-684027d07e96">

source :- VLSI System Design


Static behavior Evaluation : CMOS inverter Robustness

1. Switching Threshold, Vm is the point where Vin = Vout

<img width="1106" alt="Screenshot 2024-08-05 at 7 07 04 AM" src="https://github.com/user-attachments/assets/60d580dd-a210-41b6-91f3-c1f693b5c7fa">

Sourece :- VLSI System Dsign


Based on the Calculations of

<img width="1162" alt="Screenshot 2024-08-05 at 7 25 22 AM" src="https://github.com/user-attachments/assets/e5f30fb1-da5d-4f8d-be52-db0874c3eddc">

source :- VLSI System Design













