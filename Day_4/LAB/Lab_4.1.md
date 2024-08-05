# LAB 4.1

# here we will be trying to Create a LEF of the Inverter which we have created

Guide lines to be followed

1. Input and outputs must lie on intersection of Vertical and Horizontal tracks

2. Width of the cell must be odd multiples of horizontal Track pitch

3. Height of the cell must be odd multiples of Vertical track pitch


Now Go Inside the following Path

```
cd work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd/
less tracks.info
```

There you will see Information of all tracks, which will be used during the route Stage

<img width="1061" alt="Screenshot 2024-08-05 at 8 42 31 PM" src="https://github.com/user-attachments/assets/5adbde77-aef3-4f3d-a97e-5595b8a5f641">

Now look about the Grid Command

<img width="917" alt="Screenshot 2024-08-05 at 8 44 58 PM" src="https://github.com/user-attachments/assets/2a04eee9-8c20-4549-aa49-b25cd4d15e7f">

Base on the Track.info file, type command in tkon terminal

```
grid 0.46um 0.34um 0.23um 0.17um
```

After typing the above command the size of the Grids have been Changed

<img width="1111" alt="Screenshot 2024-08-05 at 8 48 24 PM" src="https://github.com/user-attachments/assets/1e7cedd3-e38c-4f2d-ba9b-cbee12ed3050">


### Now Check for a GuideLines

#### 1. Input and Output are on intersection of Vertical and horizontal tracks

<img width="892" alt="Screenshot 2024-08-05 at 8 49 46 PM" src="https://github.com/user-attachments/assets/38ebde56-ee34-4dbd-aa33-cfdc731103fe">

#### 2. Width must be in odd multiples of x pitch

As we can see that its in odd multiples of the size = 3x Block

<img width="608" alt="Screenshot 2024-08-05 at 8 52 06 PM" src="https://github.com/user-attachments/assets/98cfd2e9-7bfe-464c-b13e-59b4cf0c1fb4">

#### 3. height must be in odd multiples of y pitch

As we can see that its in odd multiples of the size = 9 x Block

<img width="192" alt="Screenshot 2024-08-05 at 8 53 36 PM" src="https://github.com/user-attachments/assets/f87197ab-fea9-4a3e-800c-3ae88e796fb8">


Please reffer the GIT For more Detailed Information

https://github.com/nickson-jose/vsdstdcelldesign.git


# Now Lets Extract the LEF File 

Run the command with custom name in tkon terminal

```
save sky130_cnav_inv.mag
```

Custom name mag file is defined

<img width="741" alt="Screenshot 2024-08-05 at 8 59 57 PM" src="https://github.com/user-attachments/assets/8604ef43-d49b-48b2-b2a7-1cdc57ef522e">

Now open the custom mag file

```
magic -T sky130A.tech sky130_cnav_inv.mag &
```

<img width="817" alt="Screenshot 2024-08-05 at 11 50 04 PM" src="https://github.com/user-attachments/assets/85a14984-1f97-4b87-96d0-61c840725e42">


Now lets write the LEF File name, write the command in tkon terminal

```
lef write
```

here we can notice that the Lef File has been Created

<img width="891" alt="Screenshot 2024-08-05 at 11 51 21 PM" src="https://github.com/user-attachments/assets/cda28e8d-36a8-484c-921c-34ea4fa86d02">


We can observe Lef File

<img width="710" alt="Screenshot 2024-08-05 at 11 52 40 PM" src="https://github.com/user-attachments/assets/608e5f3c-f509-435c-9841-2069738c6236">


# next task is to integrate in Our Picorv32a Flow

copy the lef into the scr directory of OpenLane

<img width="1126" alt="Screenshot 2024-08-06 at 12 00 30 AM" src="https://github.com/user-attachments/assets/3351f2a6-4f11-49a9-9abf-b1956f33fbfd">

Now basic Idea is Included in the Current Design

now we copy all the design libs to src folder

<img width="1048" alt="Screenshot 2024-08-06 at 12 04 52 AM" src="https://github.com/user-attachments/assets/0739c997-2321-4c42-8361-7f7ad66389bc">

Now modify the config.tcl, based on below modifications

<img width="1158" alt="Screenshot 2024-08-06 at 12 10 53 AM" src="https://github.com/user-attachments/assets/f0551ebf-2b62-485f-b986-129ddb85636d">













