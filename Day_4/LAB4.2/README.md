# LAB 4_2 :- Work on Timing Analysis

we will start by running the synthesis

Again run all the prep design commands

<img width="1420" alt="Screenshot 2024-08-06 at 7 57 58 AM" src="https://github.com/user-attachments/assets/e890d713-70c1-49ec-a623-bb408494769c">


If we look into the log we, can notice at some Instances the timing is violated.

<img width="537" alt="Screenshot 2024-08-06 at 7 59 34 AM" src="https://github.com/user-attachments/assets/2c9a02b2-8f45-4f05-b877-baebc7c6bb27">

There are total of 4 violations in STA.log


#### Now lets check what synth strategy is used

```
echo $::env(SYNTH_STRATEGY)
```

<img width="320" alt="Screenshot 2024-08-06 at 8 03 40 AM" src="https://github.com/user-attachments/assets/7603b467-c0d8-4a5c-a263-e725adbbb8dc">

"0" is more delay centric

now lets make it to 1, area will increase but Timing will Improve

before area :- Chip area for module '\picorv32a': 162661.004800

<img width="649" alt="Screenshot 2024-08-06 at 8 06 08 AM" src="https://github.com/user-attachments/assets/88abe5de-5854-4233-87e8-cc461a148749">

VIOLATED Time

'''
 0.15   10.00   10.00   clock clk (rise edge)
                          0.00   10.00   clock network delay (ideal)
                         -0.25    9.75   clock uncertainty
                          0.00    9.75   clock reconvergence pessimism
                                  9.75 ^ _29826_/CLK (sky130_fd_sc_hd__dfxtp_2)
                         -0.09    9.66   library setup time
                                  9.66   data required time
-----------------------------------------------------------------------------
                                  9.66   data required time
                                 -9.77   data arrival time
-----------------------------------------------------------------------------
                                 -0.10   slack (VIOLATED)

'''

Also run the following lines to check the strategy

```
echo $::env(SYNTH_BUFFERING)
echo $::env(SYNTH_SIZING)

# if it zero we will make it to 1
set ::env(SYNTH_SIZING) 1
```

<img width="332" alt="Screenshot 2024-08-06 at 8 11 24 AM" src="https://github.com/user-attachments/assets/8a445201-1067-455b-a5a1-7937fabe907d">

Also check for drive strength

```
echo $::env(SYNTH_DRIVING_CELL)
```

<img width="369" alt="Screenshot 2024-08-06 at 8 12 56 AM" src="https://github.com/user-attachments/assets/995ffdf4-6308-4153-85f5-1654b74bcb56">

Now lets set it to 8

<img width="519" alt="Screenshot 2024-08-06 at 8 13 45 AM" src="https://github.com/user-attachments/assets/4110c9fa-8664-4b33-96e5-65f734d6970b">


Now lets the run, based on these settings

```
run_synthesis
```

<img width="185" alt="Screenshot 2024-08-06 at 8 24 40 AM" src="https://github.com/user-attachments/assets/989db3cf-dd51-4b6c-be33-91ec352a61cf">


After placement run the command

<img width="488" alt="Screenshot 2024-08-06 at 8 36 32 AM" src="https://github.com/user-attachments/assets/7b3c82dc-b196-4ed4-a033-24bb1af0d9c6">

<img width="659" alt="Screenshot 2024-08-06 at 8 36 57 AM" src="https://github.com/user-attachments/assets/e5cbaec2-a9af-487f-b9e0-37adf34c92cc">


