# Lecture 1 :- Timing modelling using delay tables

# Clock Tree Synthesis

## Introduction to Delay Tables

Clock Gating cells is used, toturn off circuit when not in use

<img width="1058" alt="Screenshot 2024-08-06 at 7 25 55 AM" src="https://github.com/user-attachments/assets/f9d03365-b5d0-4cd4-826a-e3ed8f3677ef">

source :- VLSI System Design


Delay Table for CBUF '1'

<img width="521" alt="Screenshot 2024-08-06 at 7 27 42 AM" src="https://github.com/user-attachments/assets/d9091dda-f139-4639-b202-4377031a71a2">

source :- VLSI System Design


Similary we will have for all the gates in libs,

<img width="450" alt="Screenshot 2024-08-06 at 7 28 39 AM" src="https://github.com/user-attachments/assets/0d265d8c-d789-4081-b613-2df004d4fc79">

source :- VLSI System Design


To get latency we need to add the delay at each stage before the clock reaches the flop

<img width="412" alt="Screenshot 2024-08-06 at 7 32 08 AM" src="https://github.com/user-attachments/assets/ee3d22f5-44bc-41c5-be41-98bb608be8ca">

source :-  VLSI System Design


<img width="1111" alt="Screenshot 2024-08-06 at 7 33 09 AM" src="https://github.com/user-attachments/assets/e30bf95a-a86c-4524-a69f-8afc2d7cd044">

source :- VLSI System Design


We will try to achive a non zero skew



