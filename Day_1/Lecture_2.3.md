## Introduction to OpenLane

1. Started as an Open-Source flow for True Open Source Tape-out Experiment

2. striVe is a family of open everything SoCs
  Open PDK, Open EDA, Open RTL


# openLANE ASIC Flow

In the Below Image you will find the Architecture of the OpenLANE

![image](https://github.com/user-attachments/assets/6769f832-e2a5-440c-b74b-460337b5450d)

source :- https://openlane.readthedocs.io/en/latest/flow_overview.html

### Step 1 :- Synthesis

Yosys + ABC --> tool is used to Convert RTL to synthesis

### Step 2 :- DFT (Design For Test)

If we want to enable the system to ready for testing after manufacturing

Fault --> tool is used for the following tasks
1. Scan Insertion

2. Automatic Test Pattern Generation (ATPG)

3. Test Patterns Compaction

4. Fault Coverage

5. Fault Simulation


### Step 3 :-  Physical Implementation

OpenROAD --> Tool is used

Also called automated PnR (Place and Route)
  1. Floor/Power Planning
  2. End Decoupling Capacitors and Tap cells insertion
  3. Placement
  4. Post Placement Optimization
  5. CTS
  6. Routing


### Step 4 :- LEC (Logic Equivalence Checking)

Yosys --> Tool is used

### Step 5 :- Fake antenna Diodes 

Dealing with Antenna Rules Violations


### Step 6 :- Sign Off

RC Extraction is Done

STA is Verified

Physical Verification


Finally the GDS File is Genearated

![image](https://github.com/user-attachments/assets/a8bae0a6-2a56-4efc-a7af-b63617e10975)

source :- https://upload.wikimedia.org/wikipedia/commons/a/aa/Silicon_chip_3d.png
