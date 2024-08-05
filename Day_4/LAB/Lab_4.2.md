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








