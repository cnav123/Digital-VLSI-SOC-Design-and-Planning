# Lecture 2 :- Static Timing Analysis

## lets do the Timing analysis for Ideal clocks

<img width="1143" alt="Screenshot 2024-08-06 at 8 40 55 AM" src="https://github.com/user-attachments/assets/d9ef6d05-df69-4962-9dfb-7bd832750fe6">

source :- VLSI System Design

Here combinational delay must be less than the time period

Now lets consider the practical secnarion, 

lets have a look inside the Flop

<img width="983" alt="Screenshot 2024-08-06 at 8 42 11 AM" src="https://github.com/user-attachments/assets/a22c6304-9d71-4237-ba9f-8fb3ae346120">

source :- VLSI System Design

changes happen when clock changes from 0 to 1

** Hence finite time 'S' required (before clk edge) for 'D' to reach Qm **

** therefore internal delay of mux1 is = Setup time**

Now modified Timing is

<img width="1119" alt="Screenshot 2024-08-06 at 8 44 35 AM" src="https://github.com/user-attachments/assets/c6271b61-5362-4624-81ee-55e482c39415">

source :- VLSI System Design


## Clock Jitter

Window, within which clock edge can arrive on a real chip

<img width="718" alt="Screenshot 2024-08-06 at 8 46 38 AM" src="https://github.com/user-attachments/assets/9dad3bdf-56d6-4605-b0e6-b584b2c1f593">

source :- VLSI System Design


Jitter is temporary variations of clock period

<img width="729" alt="Screenshot 2024-08-06 at 8 48 40 AM" src="https://github.com/user-attachments/assets/e6f61b06-e9c4-491e-bc10-cacb3db557f7">

source :- VLSI System Design


<img width="741" alt="Screenshot 2024-08-06 at 8 48 53 AM" src="https://github.com/user-attachments/assets/aaf91b9d-ce28-454d-bfa7-d8f5ab13f440">

source:- VLSI System Design



