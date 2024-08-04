# Chip Floor Planning Considerations

## Step 1 :- Define Width and Height of Core and Die

Here we will Find width and height of the core and die

<img width="490" alt="Screenshot 2024-08-04 at 5 15 58 PM" src="https://github.com/user-attachments/assets/f6f1e238-6a68-41c5-b69d-8b4f0f2f1893">

source :- VLSI System Design

For Example consider, a netlist with 2 flops and 2 gates, with below shown connections.

note :- A "netlist" describes the connectivity of an electronic design.

<img width="888" alt="Screenshot 2024-08-04 at 5 17 57 PM" src="https://github.com/user-attachments/assets/eeccc538-728e-417b-8333-ca18d7f0833a">

source :- VLSI System Design

Now give, length and breath of the ecells

<img width="774" alt="Screenshot 2024-08-04 at 5 19 01 PM" src="https://github.com/user-attachments/assets/797833ff-40fa-44d3-8416-918ffd9065e4">


source :- VLSI System Design

Lets assume they have an area of each cell of 1square unit

A 'die', which consists of core, is small semiconductor material specimen on which the fundamental circuit is fabricated.

<img width="819" alt="Screenshot 2024-08-04 at 5 20 57 PM" src="https://github.com/user-attachments/assets/a8417336-d716-4ba2-846f-20d11c07cf42">

source :- VLSI System Design

How to arrive on its dimensions??

Place all logical cells inside the 'core'

the logical cells occupies the complete area of the core 

<img width="344" alt="Screenshot 2024-08-04 at 5 22 17 PM" src="https://github.com/user-attachments/assets/daad9b3a-29c5-4adc-b9f5-f0a4dc919c09">

source :- VLSI System Design

here we see 100% Utilization 

                     (Area Occupied By netlist)
Utilization Factor =   -------------------------
                      (Total Area of the core)


                   (Height)
Aspect Ration =   -----------
                   (width) 



## Step 2 :- Define Locations of Preplaced Cells

For example consider the Below Image, Where a combinational Logic is Broken Down to The Following Blocks

<img width="1077" alt="Screenshot 2024-08-04 at 5 27 15 PM" src="https://github.com/user-attachments/assets/28ebd2fc-84be-4489-8984-4825db680794">

source :- VLSI System Design


Now that Block is Extended and Black Boxed

<img width="947" alt="Screenshot 2024-08-04 at 5 28 42 PM" src="https://github.com/user-attachments/assets/b9f5e620-d5cb-4eea-983e-a1c646a048b4">

source :- VLSI System Design

Similarly, there are Other IP's also available, for eg..,

<img width="738" alt="Screenshot 2024-08-04 at 5 30 22 PM" src="https://github.com/user-attachments/assets/f4c449bf-9936-45c2-b4db-a0da62e60250">

source :- VLSI System Design

*The Arrangement of These IP's in a CHIP is referred as Floorplanning*

*These IP's/blocks have user-defined locations, and hence are placed in chip before automated placement-and-routing and are called as pre-placed cells*

*Automated placement and routing tools places the remaining logical cells in design onto chip*

Here we can see How pre placed cells are placed

<img width="574" alt="Screenshot 2024-08-04 at 5 33 44 PM" src="https://github.com/user-attachments/assets/6b9f0c8a-6cc3-4205-aeea-8ca9d75e53bd">

source :- VLSI System Design

## Step 3 :- Surround pre-placed cells with Decoupling Capacitors

Decoupling capacitors are used to filter out voltage spikes and pass through only the DC component of the signal. The idea is to use a capacitor in such a way that it shunts, or absorbs the noise making the DC signal as smooth as possible.

Here in the below Image You can see that **Decap** have been Placed

<img width="503" alt="Screenshot 2024-08-04 at 5 36 26 PM" src="https://github.com/user-attachments/assets/e60921f1-7f07-412d-a755-130db2409940">

source :- VLSI System Design


## Step 4 :- Power Planning

Now Consider a scenarion, Where Each cells Require a power and Ground

If we Place them Globally Then There is a chance that by the time power signal travells, then It loses its Strength
As shown below

<img width="943" alt="Screenshot 2024-08-04 at 5 40 45 PM" src="https://github.com/user-attachments/assets/7c0a9b85-c775-4780-9075-9e64453f22c9">

source :- VLSI System Design

For Example :- 

<img width="970" alt="Screenshot 2024-08-04 at 5 45 34 PM" src="https://github.com/user-attachments/assets/b727b881-4ac8-4759-b99c-887c43ea6279">

source :- VLSI System Design


<img width="951" alt="Screenshot 2024-08-04 at 5 45 48 PM" src="https://github.com/user-attachments/assets/ff2235a7-95b1-4abb-bed7-f3b9f37008bc">

Source :- VLSI System Design

**The soulution is make grid structure for VDD and VSS**
The gets power from the Near by power point and gnd from near by ground point

<img width="1032" alt="Screenshot 2024-08-04 at 5 47 07 PM" src="https://github.com/user-attachments/assets/046df807-a201-4c86-840d-488d4755a4e1">

source :- VLSI System Design


## Step 5 :- Pin Placement

Consider the Below Example

<img width="916" alt="Screenshot 2024-08-04 at 5 49 44 PM" src="https://github.com/user-attachments/assets/b03ec8e1-7e4c-4953-ace0-aa1b0c344a49">

<img width="912" alt="Screenshot 2024-08-04 at 5 50 18 PM" src="https://github.com/user-attachments/assets/53305b16-ee7c-4344-9f7d-ec5b5d740fb5">

source :- VLSI System Design

here Block is a preplaced Cells

The below image shows the pin Placement

<img width="1059" alt="Screenshot 2024-08-04 at 5 51 22 PM" src="https://github.com/user-attachments/assets/2fbb9dff-96a1-4e37-8589-b221eb386920">

source :- VLSI System Design

Now Floorplan is ready for Placement

## Step 6 :-  Logical Cell placement Blockage

