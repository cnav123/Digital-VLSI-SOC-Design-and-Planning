# Lecture 3 :- LAB Exercise : Magic

## Here we will be using the Google/Sky Water DRC rules

You can look for magic documentation in the following link, for more detailed Rules 

http://opencircuitdesign.com/magic/index.html

## Google skywater 130 documentation 

Here you can look for detailed information

https://github.com/google/skywater-pdk

https://skywater-pdk.readthedocs.io/en/main/


## Magic DRC

To work on the various small labs pre copy the file to your directory

```
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
tar xfz drc_tests.tgz
```

You see various data, to actually work you need to copy the sky130 tech file to the drc_tests directory

```
cp -rf /work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech ./
```

with the help of the you will be able to work with magic tool

## Now look at the simple fiele met3.mag

```
magic met3.mag
```

<img width="1127" alt="Screenshot 2024-08-05 at 5 39 08 PM" src="https://github.com/user-attachments/assets/ca159469-ee13-4a27-ba79-0a8c981e24c9">

In the above documentation we can look at the various DRC rules


### drc why to just have a look at the Design

![Screenshot 2024-08-05 at 5 43 32 PM](https://github.com/user-attachments/assets/2dbcf16f-21db-4d7c-90e4-c93711b128cb)

here we can look thet m3.1 and m3.2 are violated

## Exercise 1

load the poly.mag file

<img width="520" alt="Screenshot 2024-08-05 at 5 48 11 PM" src="https://github.com/user-attachments/assets/e5cee322-e7ba-4b3d-8745-40b18cb2dd27">

You will get the Following output

<img width="1440" alt="Screenshot 2024-08-05 at 5 48 38 PM" src="https://github.com/user-attachments/assets/f002f157-1bf4-44d3-bfa3-88fd672531b4">



