# Magic 

VLSI Design Software 
It's a layout tool
Refer The Below link to get Information about the tool

http://opencircuitdesign.com/magic/index.html

## Link for Detailed Steps

You can reffer the Following Youtube Link for Installation.
https://youtu.be/5WzayqWoJ_w?si=zCNuOep-xMHQ96eS


# Installation Requirements
1. Command Line Tols
2. XQuartz
3. tcl/tk
4. magic

In your home 
create a directory name open_ckt_design(ocd) or name of your choice.

open terminal in mac
```
mkdir ocd
cd ocd
```

## Command Line Tools 

To install mac os Command Line Tools copy the below command in your mac os terminal
```
xcode-select --install
```

## Xquartz installation

Follow this Link to Install
https://www.xquartz.org/
download the pkg file for Instalation


## Tcl and Tk installation

here a breif Info 
https://wiki.tcl-lang.org/page/Apple+Macintosh+and+Tcl%2FTk

Inside the ocd diectory in the Terminal
```
wget https://prdownloads.sourceforge.net/tcl/tcl8.6.10-src.tar.gz
wget https://prdownloads.sourceforge.net/tcl/tk8.6.10-src.tar.gz
```

Now unzip Everything
```
gunzip *gz
tar -xf *tar
```
### Instalation of Tcl
After Extration
```
cd tcl8.6.10
```
Note :- Don't Go to the macos Folder, Instead Prefer the UNIX folder

```
cd unix
```

Run the Following Lines to Install
```
./configure --prefix=/usr/local/opt2/tcl-tk
make
sudo make install
```
During sudo make Install, It will ask for device password

If Installed Sucessfully you will not get any make Errors in the terminal

### Instalation of Tk
now go back to the ocd directory and enter tk8.6.10
```
cd tk8.6.10
```
Similarly go Into UNIX Folder
```
cd unix
```

Note:- There is a BUG in the makefile 
```
code Makefile
```
This can be identified In the Line number 54 I Think.

change the line containing 
```
LIB_RUNTIME_DIR = $(libdir):/opt/x11/lib
```
to 
```
LIB_RUNTIME_DIR = $(libdir)
```
save the file
and

Run the Following commands
```
./configure --prefix=/usr/local/opt2/tcl-tk \
--with-tcl=/usr/local/opt2/tcl-tk/lib --with-x \
--x-includes=/opt/X11/include --x-libraries=/opt/X11/lib  
make
sudo make install  
```


## magic Instalation
Now copy the git Repo to your directory
```
cd
cd ocd
git clone git://opencircuitdesign.com/magic
cd magic
```

now run the Folloeing commands 
```
./configure --with-tcl=/usr/local/opt2/tcl-tk/lib \
--with-tk=/usr/local/opt2/tcl-tk/lib \
--x-includes=/opt/X11/include \
--x-libraries=/opt/X11/lib \
CFLAGS=-Wno-error=implicit-function-declaration
make
sudo make install
```


Now type 
```
magic
```
you will get a pop up Window
