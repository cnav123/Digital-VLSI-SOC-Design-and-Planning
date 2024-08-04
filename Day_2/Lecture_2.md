# Lecture 2 :- Library Binding and Placement

## Netlist Binding and Initial place design

### Step 1 :- Bind netlist with physical cells

In the Below Image you can find that

<img width="710" alt="Screenshot 2024-08-04 at 6 42 21 PM" src="https://github.com/user-attachments/assets/e3bdcb22-fb5e-4c76-b423-2fd42bb9855c">

cell names of Different sizes and color, They also have a different delays models, Based on the requirement we can use

### Step 2:- Placement

In the Below Image we can Find How the placement is done.

<img width="592" alt="Screenshot 2024-08-04 at 6 46 40 PM" src="https://github.com/user-attachments/assets/e57a67bd-e6ec-4937-836d-8d121ac45430">

source :- VLSI System Design


### Step 3 :- Optimize Placement

In this Stage where we estimate wire Length and capacitance and, based on that, insert repeaters

Here is the Final Placement looks

<img width="1180" alt="Screenshot 2024-08-04 at 6 49 46 PM" src="https://github.com/user-attachments/assets/aa733007-b408-443d-a7dd-6c66d189688c">

source :- VLSI System Design


Now, we have to check weather the Placement done is optimazed or not

By doing Setup timing Analysis (STA) based on those values with Ideal clock, weather placement is write or not


