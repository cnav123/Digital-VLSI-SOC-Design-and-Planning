# LAB 5

## Will Start With Power Generation and Distribustion Network

Run the design upto cts

![Screenshot 2024-08-09 at 2 07 51 PM](https://github.com/user-attachments/assets/71d26259-bcd8-458f-9d79-b7638ecca0db)

Then Type the commnad

```
gen_pdn
```
![Screenshot 2024-08-09 at 2 09 50 PM](https://github.com/user-attachments/assets/5c3d365a-9400-4222-a52c-cd6416fdb724)

The generated def is In the following Path

![Screenshot 2024-08-09 at 2 14 13 PM](https://github.com/user-attachments/assets/b3c014ce-4cec-49b7-bddb-8dfecd711dc1)

Now using the Magic Command,

```
magic -T ../../../../../../vsdstdcelldesign/sky130A.tech led read ../../tmp/merged.nom.lef def read picorv32a.def
```

<img width="1426" alt="Screenshot 2024-08-09 at 2 17 31 PM" src="https://github.com/user-attachments/assets/d91a38d6-94f2-4736-9eb6-5255efbd10bc">

After Zooming

<img width="726" alt="Screenshot 2024-08-09 at 2 18 00 PM" src="https://github.com/user-attachments/assets/b6657298-609b-4bee-9e02-fa1eeee98131">

Now type the comand in tkon terminal,

```
expand
```

<img width="772" alt="Screenshot 2024-08-09 at 2 18 34 PM" src="https://github.com/user-attachments/assets/c9126a47-5ed4-42d5-bf31-88ab71858440">
