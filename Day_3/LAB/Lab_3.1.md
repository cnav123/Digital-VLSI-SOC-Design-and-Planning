Hi 

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










