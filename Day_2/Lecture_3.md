# Lecture 3 :- Cell Design Flow & Charecterization Flow

# Cell Design Flow

## Inputs for Cell Design Flow

The Library consists of Same cells with Different Functionality, Different Sizes and Different Voltages

<img width="1073" alt="Screenshot 2024-08-04 at 7 26 41 PM" src="https://github.com/user-attachments/assets/a318c1fe-121b-4c72-a402-c44a519464b1">

source :- VLSI System Design

Cell Design Flow Has Three Steps

1. Inputs

2. Design Steps

3. Outputs

### Inputs

It mainly Consists of Proess Design Kits(PDKs):

DRC & LVS rules, SPICE Models, Library & user-defined specs


### Design Steps

1. Circuit Design 

2. Layout Design --> Stick diagram of Circuit + Eulers Path

3. Charecterization



### Outputs

The final output is CDL file (Circuit description language),

GSDII, LEF, Extracted Spice netlist(.cir)

Timing, noise, power .libs, function

****



Adding an Image for The Flow

<img width="688" alt="Screenshot 2024-08-04 at 7 36 02 PM" src="https://github.com/user-attachments/assets/e6e9caba-695d-452c-ba3d-a41547f1789e">

source :- VLSI System Design



# Characterization Flow

Step 1 :- Read the model file

Step 2 :- Read the extracted spice netlist

Step 3 :- Define the behaviour of the ckt

Step 4 :- read the Sub ckt ot the Design

Step 5 :- Attatch the Necessary power sources

Step 6 :- Apply the Stimulus

Step 7 :- Apply the required Capacitance

Step 8 :- provide the Nececarry simulation

