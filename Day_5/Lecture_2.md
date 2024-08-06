# Lecture 2 :- Triton Route

## Features of Triton Route

1. Performs initial detail route

2. Honors the preprocessed route guides (obtained after fast route) i.e, attempts as musch as possible to route within route guides.

3. Assumes route guides for each net satisfy inter-guide connectivity.

4. Works on proposed MILP-based panel routing scheme with intra-layer parallel and inter-layer sequential routing network.

### Preprossed route guides

<img width="1053" alt="Screenshot 2024-08-06 at 12 10 02 PM" src="https://github.com/user-attachments/assets/39504b61-22bc-4b5f-914b-ee20037a251a">

source :- VLSI System Design


Requirements of preprossed guides are,

  1. Should have unit width

  2. Should be in the preferred direction.


### Inter-guide connectivity

Two guides are connected if :

  1. they are on the same metal layer with touching edges, or

  2. they are on neighboring metal layer with nonzero vertically overlapped area.

Each unconnected terminal (i.e.., pin of a standard- cell instance should have its pin shape overlapped by a route guide.)


### Routing has two main stages

<img width="1306" alt="Screenshot 2024-08-06 at 12 17 57 PM" src="https://github.com/user-attachments/assets/6043ecd7-1b6b-4239-ba77-e36cb5ca5e67">

source :- VLSI System Design


### Intra-Layer Parallel & Inter-Layer sequential panel routing

<img width="1009" alt="Screenshot 2024-08-06 at 12 18 53 PM" src="https://github.com/user-attachments/assets/fd51f3fa-ec99-41df-9926-a30803661cc8">

source :- VLSi System Design


### TritonRoute 

Inputs :- LEF, DEF, Preprocessed route guides

Outputs :- Detailed routing solution with optimized wire-length and via count

Constraints :- Route guide honoring, connectivity constraints and design rules.


### Handling Connectivity

<img width="885" alt="Screenshot 2024-08-06 at 12 22 45 PM" src="https://github.com/user-attachments/assets/3996929f-9423-4b48-8b1a-1b866160c509">

source :- VLSI System Design


  Access Point (AP) :- An on-grid point on the metal layer of the route guide, and is used to connect to lower-layer segments, upper-layer segments, pins or IO ports.

  Access Point Cluster (APC) :- A union of all Aps derived from same lower-layer segment, upper-layer guide, a pin or an IO port.


### Routing technology ALgorithm

<img width="653" alt="Screenshot 2024-08-06 at 12 27 45 PM" src="https://github.com/user-attachments/assets/a4d57db1-d674-4962-9164-14c65f5163f1">

source :- VLSi System Design


