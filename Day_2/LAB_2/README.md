# LAB 2

Here I am adding the the run Folder

## Please Give look into the configuration directory, inside the OpenLane Directory

Now open the floorplan.tcl, and have look into the utilization Factors etc..,

<img width="724" alt="Screenshot 2024-08-04 at 5 59 02 PM" src="https://github.com/user-attachments/assets/0428ca78-d30c-4961-a993-c21f07fee7b9">

### here we have default Utilization of "50%"

Now open the config.tcl inside the Design picorv32a and add the follwing Lines
```
set ::env(CLOCK_NET) $::env(CLOCK_PORT)
set ::env(FP_CORE_UTIL) 65
set ::env(FP_IO_VMETAl) 4
set ::env(FP_IO_HMETAl) 3
```
Note :- In the OpenLane Floor the VMETAL and HMETAl is one more That what we specify

That means VMETAL = 4 + 1 =5

That means VMETAL = 3 + 1 =4


Here using the tool we will work on Developing the Floor Plan for the design

It can be run by typing the command

```
run_floorplan
```

<img width="960" alt="Screenshot 2024-08-04 at 6 06 01 PM" src="https://github.com/user-attachments/assets/2d9e4157-fa74-463c-852e-7ea682457b39">

Now Check weather the changes made on config.tcl have actually made on the design

There a config.tcl inside the runs directory

<img width="1433" alt="Screenshot 2024-08-04 at 6 12 14 PM" src="https://github.com/user-attachments/assets/781fcd77-ddd2-4dd9-ac5c-e673434ed331">

There we can see that there is core utilization of 35%, reason being 

The reason Being that, inside the designs/picorv32a/ sky130A_sky130_fd_sc_hd_config.tcl file has core utilization of 35% as shown in the below Image, 
There for Its has been overwritten

<img width="1116" alt="Screenshot 2024-08-04 at 6 13 40 PM" src="https://github.com/user-attachments/assets/76445524-4b11-4d3c-aa58-8076068d8e9e">

Now to Check the Design In the Magic tool

```
cd /OpenLane/designs/picorv32a/runs/RUN_2024.08.04_10.18.07/results/floorplan
```

Ther you can see the .def file

<img width="725" alt="Screenshot 2024-08-04 at 6 20 12 PM" src="https://github.com/user-attachments/assets/abdd958f-da08-4100-bc80-dd23ff7e746a">

Assignement1 :-  ** Area of the Chip is **

** ans :- x= 692760/1000 = 692.76
          y= 703480/1000 = 703.48
          area = x*y = 487342.8048 Square Micron **

Now to Check the Layout after FloorPlan

```
magic -T work/tools/openlane_working_dir/pdk/sky130A/libs.tech/magic/sky130A.tch lef read ../../tmp/merged_nom.lef def read picorv32a.def
```
<img width="981" alt="Screenshot 2024-08-04 at 6 27 33 PM" src="https://github.com/user-attachments/assets/1b863677-7a6c-43a8-a01c-86791f1f0ff8">

After typing Enter we get the Following Informations

<img width="1213" alt="Screenshot 2024-08-04 at 6 29 00 PM" src="https://github.com/user-attachments/assets/98709b14-33b5-4fbc-9da9-47b1caef5df3">

Here In the Below Image we can the Input Pin which are equi-distant from each other

<img width="851" alt="Screenshot 2024-08-04 at 6 30 01 PM" src="https://github.com/user-attachments/assets/115bec31-4174-43a7-962f-72dcdf6ca7b0">

here is Information from tkon

<img width="944" alt="Screenshot 2024-08-04 at 6 32 57 PM" src="https://github.com/user-attachments/assets/aa02a509-2fbb-4e9d-b144-8c25aee449c7">

<img width="889" alt="Screenshot 2024-08-04 at 6 34 41 PM" src="https://github.com/user-attachments/assets/8cdce7ca-eec6-4ee6-a78d-6dfb45c1a642">
