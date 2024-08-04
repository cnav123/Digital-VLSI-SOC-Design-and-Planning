# LAB 1 

Hi Run Data has also been Uploaded 

Only Synthesis Stage is Present


## Basic Introduction


After Installing the tools from the Instalation Directory You can start with basic commands to get a feel of the tools\

```
cd Openlane
```

copy the "picorv32a" design from work/designs/ in the repo

to

the design directory in the Openlane directory

## Setup the Design

Go Into the Directory Openlane and Type the Following commands

```
cd OpenLane
make mount
```
Here we will go into the docker openLane Container

<img width="993" alt="Screenshot 2024-08-04 at 3 37 14 PM" src="https://github.com/user-attachments/assets/263a7bba-b8e6-4959-ae87-db82109975b5">

now type
```
./flow.tcl -interactive
```

<img width="971" alt="Screenshot 2024-08-04 at 3 38 26 PM" src="https://github.com/user-attachments/assets/da816744-72c7-43e0-84eb-30ebc9460e91">

now give all the packages to run the flow

```
package require openlane 0.9
```

<img width="954" alt="Screenshot 2024-08-04 at 3 40 05 PM" src="https://github.com/user-attachments/assets/ff5d81ef-76d6-468e-ae99-b103a72f0bac">


## Design Information

Now go Inside the #Picorv32a design,

there you find scr dirctory (where .v and .sdc files are present)
pdk file --> sky130A_sky130_fd_sc_hd_config.tcl
configuration file --> config.tcl

If we Open the config.tcl we will find

```
# Design
set ::env(DESIGN_NAME) "picorv32a"

set ::env(VERILOG_FILES) "./designs/picorv32a/src/picorv32a.v"
set ::env(SDC_FILE) "./designs/picorv32a/src/picorv32a.sdc"

set ::env(CLOCK_PERIOD) "20.000"
set ::env(CLOCK_PORT) "clk"


set ::env(CLOCK_NET) $::env(CLOCK_PORT)




set filename $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/$::env(PDK)_$::env(STD_CELL_LIBRARY)_config.tcl
if { [file exists $filename] == 1} {
	source $filename
}

```


Order of Heirarchy in OpenLane is

OpenLane Default < config.tcl < sky130A_sky130_fd_sc_hd_config.tcl

<img width="1067" alt="Screenshot 2024-08-04 at 3 45 47 PM" src="https://github.com/user-attachments/assets/0b34ca1a-8246-408f-889d-4a01adec6791">

as we have set clock period to 20 in config.tcl

but in sky130A_sky130_fd_sc_hd_config.tcl we have period of 24.73

24.73 is the actual clock of the design

Now to prep the design 
```
prep -design picorv32a
```

<img width="959" alt="Screenshot 2024-08-04 at 3 48 27 PM" src="https://github.com/user-attachments/assets/2c6d9f87-5269-4ebf-9582-bd2b3cc80dfd">

After ruunig the command a new directory is created inside the 
path ;- 

OpenLane/designs/picorv32a/runs/RUN_DTAE_TIME/TEMP/ 

you can find the merged lef

<img width="877" alt="Screenshot 2024-08-04 at 3 51 49 PM" src="https://github.com/user-attachments/assets/01ef406d-559f-4d90-b490-bae37eff2f65">

It consist the information about the wire, layers and cell level Informmation ot technical LEF


A results directory, reports and log files have been created as no operation is performed its empty

<img width="872" alt="Screenshot 2024-08-04 at 3 53 46 PM" src="https://github.com/user-attachments/assets/bd01c56e-3318-48f2-8f35-93dea15dc67e">

## Step 1 :- Synthesis

```
run_synthesis
```

<img width="967" alt="Screenshot 2024-08-04 at 3 56 16 PM" src="https://github.com/user-attachments/assets/a67ad59c-be58-4965-88c4-bc3a76726066">

```
synthesis is completed
```

After the sysnthesis is completed the log Files have been Generated

# Objective : - Calculate the Flop Ration for the Total number of cells

From bellow Image we can observe that 

<img width="1051" alt="Screenshot 2024-08-04 at 3 59 47 PM" src="https://github.com/user-attachments/assets/cbbbccb7-da0a-4ed9-b063-3c5463e49048">

the total nuber of ## D Flip Flops are = 1613
the total number of cells are  = 16558

# Flop ration = 1613/16558 = 0.097 (9.7%)



Here you can also find the Chip area

<img width="750" alt="Screenshot 2024-08-04 at 4 02 08 PM" src="https://github.com/user-attachments/assets/48df593e-b554-46fc-9ed8-a230018a70c3">
