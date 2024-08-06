# Now Lets Begin The flow with custom tcl that has been added to the Design

Go to Openlane Floder and run the Following Commands

```
make mount
# Openlane Container is opned
./flow.tcl -interactive

# Add the required package
package require openlane 0.9
prep -design picorv32a
```
** note :- If we want to overwrite the Exsisting Run directory Then type the following command **

```
prep -design picorv32a -tag <past_run_directory_name> -overwrite
```

<img width="1081" alt="Screenshot 2024-08-06 at 12 17 37 AM" src="https://github.com/user-attachments/assets/c8ebb0ad-b1af-43dd-becb-d17517c052f9">

Now add these comands in the flow

```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]

add_lefs -src $lefs
```

<img width="1036" alt="Screenshot 2024-08-06 at 12 20 36 AM" src="https://github.com/user-attachments/assets/ed2a07ae-0c39-42dd-8445-aa270412980b">

here in typical lib our cell is added

<img width="1092" alt="Screenshot 2024-08-06 at 12 33 32 AM" src="https://github.com/user-attachments/assets/cee4a27f-0cd7-439d-9535-512d87644633">


## Run Synthesis 

```
run_synthesis
```

<img width="1103" alt="Screenshot 2024-08-06 at 12 22 23 AM" src="https://github.com/user-attachments/assets/b00bc30e-ba6b-45f8-a790-eb0c457d94fd">

Now lets Check the Log  files, Wether the custom inverter has been added or not

![Screenshot 2024-08-06 at 6 57 54 PM](https://github.com/user-attachments/assets/2bed7a2f-e823-4b3f-ad71-7c6382ae48df)


Here we can notice that 145 cells have been added with custom name

now after running the placement You can check,

<img width="1239" alt="Screenshot 2024-08-06 at 7 13 07 PM" src="https://github.com/user-attachments/assets/b341640c-1801-4dda-aa9b-65b605e14b95">

Now lets select the cell and expand them,

<img width="839" alt="Screenshot 2024-08-06 at 7 13 53 PM" src="https://github.com/user-attachments/assets/df22f10f-7c90-4d7b-9a84-1d55a497ac01">


## Now we have to verify for the, slack is met or not

now create a pre_sta.conf file for the 

```
set_cmd_units -time ns -capacitance pF -current mA -voltage V -resistance kOhm -distance um
read_liberty -max /Users/akhilvarma/OpenLane/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read_liberty -min /Users/akhilvarma/OpenLane/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
read_verilog /Users/akhilvarma/OpenLane/designs/picorv32a/runs/RUN_2024.08.06_13.36.20/results/synthesis/picorv32a.v
link_design picorv32a
read_sdc /Users/akhilvarma/OpenLane/designs/picorv32a/src/picorv32a.sdc
report_checks -path_delay min_max -fields {slew trans net cap input_pin}
report_tns
report_wns

```

![Screenshot 2024-08-06 at 7 22 44 PM](https://github.com/user-attachments/assets/3e076656-1dcf-4267-8dba-1c4b4d800ac8)


Now manually set the Fan out value

![Screenshot 2024-08-06 at 7 27 20 PM](https://github.com/user-attachments/assets/f3bb9862-a74b-465e-9ba7-8edfc0f453ef)

Here we can note that all the Slew is met
![Screenshot 2024-08-06 at 7 28 54 PM](https://github.com/user-attachments/assets/4190769f-565d-4f62-ac9a-12d9560b6b29)


## now Lets Start Working on Clock Tree Synthesis

For running the CTS its will take the Default value, from configuration

<img width="1151" alt="Screenshot 2024-08-06 at 7 42 56 PM" src="https://github.com/user-attachments/assets/59971bc5-8fbe-4083-a947-4f5f4a2c65cf">

source :- VLSI System Design

![Screenshot 2024-08-06 at 7 44 38 PM](https://github.com/user-attachments/assets/f66b7951-3d70-403e-adca-40cf180e7eee)

now lets run the cts

![Screenshot 2024-08-06 at 7 45 49 PM](https://github.com/user-attachments/assets/0944492c-d13d-4c21-b029-0bd9e0058354)

Now lets verify the Design

