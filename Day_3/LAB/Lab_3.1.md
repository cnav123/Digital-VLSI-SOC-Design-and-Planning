Hi 

I will adding all the Design Files here

vsdstdcelldesign Directory Here

## For Detailed Understanding Please follow the following Link

https://github.com/nickson-jose/vsdstdcelldesign.git

Here is the Detailed Step for Creating the required CMOS Inverter mag file


here we will working on cloning from the git 

Into your OpenLane Directory

```
git clone https://github.com/nickson-jose/vsdstdcelldesign.git
```

Here you will find files related to the project

<img width="1079" alt="Screenshot 2024-08-05 at 7 30 38 AM" src="https://github.com/user-attachments/assets/86873935-4ece-4940-b68d-c64d2e76938c">

To open the .mag file we need to have the magic tech file,

For ease of use we copy the tech file into the vsdstdcell design folder

```
cp -rf ../../Desktop/Education/Digital\ VLSI\ SoC\ Design\ \&\ Planning/LABS/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech ./

```

Here we can see that file has been added

<img width="1051" alt="Screenshot 2024-08-05 at 7 34 20 AM" src="https://github.com/user-attachments/assets/8b7e82ed-37b5-410d-b0c5-406f4afe98de">


Now Invoke the magic tool

```
magic -T sky130A.tech sky130_inv.mag &
```

Here we get layout of the following Diagram

<img width="1128" alt="Screenshot 2024-08-05 at 7 36 32 AM" src="https://github.com/user-attachments/assets/63f5d128-5ed0-4293-911a-f8e11171dace">


Move the Cursor on the Green Region, and Press "s" in key board and go to tkob terminal You will get Information about the Cells

<img width="1242" alt="Screenshot 2024-08-05 at 1 37 59 PM" src="https://github.com/user-attachments/assets/c87dccdd-385e-425f-8231-7279caf86006">

Here we can observe the various connection that are There, WHich are required for the inverter to work

** Note:- magic is an Interactive DRC tools where Its shows the DRC Violations on the go **


Now extract the file, by typing the following command

```
extract all
```
You will get the following output

![Screenshot 2024-08-05 at 2 15 43 PM](https://github.com/user-attachments/assets/2f27ffde-9a9b-46b8-9607-fb30b077022b)

## Now to run In the ngspice tool we need spice Netlist

Now run the following command

```
ext2spice cthresh 0 rthresh 0
```
by running the above command we will also extract the capacitance values also

now again the run
```
ext2spice
```
The required spice file is Generated

![Screenshot 2024-08-05 at 2 20 28 PM](https://github.com/user-attachments/assets/866a5cc8-b71f-48ff-8b1a-b920342b6c78)

Now create a file Containing the Following

file Name :- cnav_inv.spice

** note:- we need to Include th lib FIles also**

which can be found ./libs/ pathe

![Screenshot 2024-08-05 at 3 51 03 PM](https://github.com/user-attachments/assets/37dafce2-7e11-465d-8fe4-1c200f010275)


```
* SPICE3 file created from sky130_inv.ext - technology: sky130

.option scale=10000u

.include ./libs/nshort.lib
.include ./libs/pshort


//.subckt sky130_inv A Y VPWR VGND (No need for This Line)
M1000 Y A VPWR VPWR pshort_model.0 w=37 l=23 ad=1443 pd=152 as=1517
M1001 Y A VGND VGND nshort_model.0 w=35 l=23 ad=1435 pd=152 as=1365 ps=148

VDD VPWR 0 3.3V

VSS VGND 0 0V

// trigger Input Signal
Va A VGND PULSE(0V 3.3V 0 0.1ns 0.1ns 2ns 4ns)

C0 A Y 0.05fF
C1 Y VPWR 0.11fF
C2 A VPWR 0.07fF
C3 Y 0 0.24fF
C4 VPWR 0 0.59fF
//.ends (no need )

// Now run the Transisent Analysis
.tran 1n 20n

.control
run
.endc
.end
```

The following File is Generated with the above contents

![Screenshot 2024-08-05 at 3 48 30 PM](https://github.com/user-attachments/assets/60a78991-b634-4648-9d11-75cd5c2fcd84)


# NGSPICE Simulations

to run the File invoke ngspice along with the file
```
ngspice cnav_inv.spice
```
After Running you will get the following output

![Screenshot 2024-08-05 at 3 58 00 PM](https://github.com/user-attachments/assets/0f134061-e56e-4bfc-9f8a-c5d82e6ac816)

## Now to check the waveform

```
plot y vs time a
```

Here we will get the Following output

<img width="721" alt="Screenshot 2024-08-05 at 3 59 51 PM" src="https://github.com/user-attachments/assets/dc059f19-b533-428c-a11e-fd45e00f67c1">


## Now we have to charecterize the cell 

we need 4 parameters that is
1. Rise Transition --> Time taken by the output waveform to rise from 20% to 80% of max value VDD

2. Fall Transition --> Time taken by the output waveform to fall from 80% to 20% of max value VDD

3. Fall cell Delay --> Propagation Delay when output is Falling (50% of output fall - 50% of input rise)

4. Rise cell Delay --> Propagation delay when output is Rising (50% of output rise - 50% of input fall)


### Now we will calculate Rise Transition Delay

for the rise of output

20% of 3.3 is = 0.66v
80% of 3.3 is = 2.64v

####Here we have zoomed for 0.66v 0r 66mV

![Screenshot 2024-08-05 at 4 10 13 PM](https://github.com/user-attachments/assets/71d5f493-b5a7-4d0e-9da7-7da7d01ac2dd)

Now seclecting the red line at 660mV line, ng spice will give Plot Values

![Screenshot 2024-08-05 at 4 12 21 PM](https://github.com/user-attachments/assets/e6501a73-dced-410c-b5af-340268878e40)

For 0.66093V the time is = 2.1635ns

####Now //y we will look for 80% value

![Screenshot 2024-08-05 at 4 15 30 PM](https://github.com/user-attachments/assets/91e0dbb6-eef3-4b68-b884-bcecce951320)

Now seclecting the red line at 2.64V line, ng spice will give Plot Values

![Screenshot 2024-08-05 at 4 16 15 PM](https://github.com/user-attachments/assets/d5875e59-fd8a-4d1d-b629-f0d0e3d84653)

For 2.64 the time is = 2.20484ns

Now the Differencr Between them will give the Rise TIme

** Rise Time = 2.20484ns - 2.1635ns = 0.0413ns = 41.3ps(pico sec) **

### Now we will Calculate the Fall Transition Time

For the Fall signal of output

20% of 3.3 is = 0.66v
80% of 3.3 is = 2.64v

Here is the Zoomed Version for 80% fall

![Screenshot 2024-08-05 at 4 21 38 PM](https://github.com/user-attachments/assets/56154f4d-ed90-45d2-849c-c8efd66b09f7)

Now seclecting the red line at 2.64V line, ng spice will give Plot Values

![Screenshot 2024-08-05 at 4 22 11 PM](https://github.com/user-attachments/assets/d39a3399-5143-49eb-8afa-87fa41ae2305)

For 2.64v time is = 4.0405ns

#### Now look for 20% value

![Screenshot 2024-08-05 at 4 23 35 PM](https://github.com/user-attachments/assets/80aa2773-6716-4639-8b3c-f8a66dd2a925)

Now seclecting the red line at 660mV line, ng spice will give Plot Values

![Screenshot 2024-08-05 at 4 24 13 PM](https://github.com/user-attachments/assets/731a04d2-aed9-4502-9c97-dc518bdd82c9)

For 0.66v time is = 4.06831ns

** Fall Time = 4.06831ns - 4.0405ns = 0.02781ns = 27.81ps(pico sec) **


### Now we will calculate the cell rise delay

Propagation delay when output is falling = 50% of the output rise - 50% of input fall

50% of 3.3v = 1.65v

Now here is the Image for the 1.65 of 
![Screenshot 2024-08-05 at 4 46 51 PM](https://github.com/user-attachments/assets/bd20113c-4f97-4e4e-ae3d-c99b3b88e673)

Here, If we select we get Following values in the ngspice tool

![Screenshot 2024-08-05 at 4 50 02 PM](https://github.com/user-attachments/assets/90f8fbb7-7721-478e-a350-cfa24c073d2c)

50% rise output = 2.18592ns at time = 1.65021

50% fall input = 2.15042ns at time = 1.64979

** cell rise delay = 2.18592ns - 2.15042ns = 0.3552ns = 355.2ps(pico sec) **

### Now we will calculate the Cell Fall Delay 

Propagation delay when output is falling = 50% of the output fall - 50% of input rise

50% of 3.3v = 1.65v

![Screenshot 2024-08-05 at 4 58 42 PM](https://github.com/user-attachments/assets/eddc116c-daf4-4061-b4e5-cb840e869e3a)


here is the Screen Shot of the values

![Screenshot 2024-08-05 at 4 57 05 PM](https://github.com/user-attachments/assets/24c1d8a2-70cb-494b-b857-645110bcc46b)

50% of output fall = 4.05518ns at time = 1.65948

50% of input rise = 4.0506 at time = 1.65974

** cell fall delay = 4.05518ns - 4.0506ns = 4.58ps (pico sec) **

Note ;- all this at room temperature 27 degree celcius
