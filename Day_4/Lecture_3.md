# Lecture 3 :- Timing Analysis with Real Clocks

## Setup Timing Analysis with Real CLock

Now the original Design is modified Into, a design with clock buffers

<img width="1371" alt="Screenshot 2024-08-06 at 11 32 29 AM" src="https://github.com/user-attachments/assets/b09c273c-8e15-40e4-b7bc-0845e0085362">

source :- VLSI System Design


Now the Formula is Modified Into, 1,2,3 &4 are buffer Delay values, what happens is Clock is shifted from 0 to 0+delta delay

<img width="947" alt="Screenshot 2024-08-06 at 11 33 34 AM" src="https://github.com/user-attachments/assets/85c134a3-7b1c-4a4a-9a1d-e58c5c75b4c7">

source:- VLSI System Design

Now the New Equation is

<img width="1343" alt="Screenshot 2024-08-06 at 11 35 18 AM" src="https://github.com/user-attachments/assets/c20140b4-bf1e-4578-8aaa-4d86bfb04162">

source :- VLSI System Design


Slack is also calculated as Follows

<img width="1179" alt="Screenshot 2024-08-06 at 11 36 01 AM" src="https://github.com/user-attachments/assets/482cc84f-5f4c-41a2-accb-911c9488982a">

Source:- VLSi System Design



## Hold Timing Analysis

Hence finite time 'H' required (after clk edge) for 'Qm' to reach to Q

** Internal delay of Mux3 = hold Time **

<img width="1151" alt="Screenshot 2024-08-06 at 11 38 15 AM" src="https://github.com/user-attachments/assets/fb8c79b2-1a43-4e34-a13e-3339f491d2a3">

source :- VLSI System Design


In Ideal case It Becomes

<img width="1264" alt="Screenshot 2024-08-06 at 11 38 59 AM" src="https://github.com/user-attachments/assets/e401fe91-2dc5-4fac-b7f5-7e378c0ff6f1">

source :- VLSI System Design


In case of Real Clocks

<img width="1243" alt="Screenshot 2024-08-06 at 11 39 33 AM" src="https://github.com/user-attachments/assets/d89133d1-cf73-46f1-bd74-6842c4385a23">

source :- VLSI System Design


Now adding the uncetanity The Values are modified to

<img width="1373" alt="Screenshot 2024-08-06 at 11 41 12 AM" src="https://github.com/user-attachments/assets/4ad5efec-9d41-42eb-a4fb-e22951f480c6">

source :- VLSI System Design



