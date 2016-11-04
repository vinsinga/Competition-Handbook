# Compiling and Running Code

### Java
#### Compile
``` Bash
javac ./filename.java
```
#### Run
``` Bash
java classname
```
### Python
#### Run
``` Bash
python ./filename.py
```
### C++
#### Compile
``` Bash
gcc ./filename.cpp
```
#### Run
``` Bash
./filename
```
***Name of program can change based on configuration of `ld` and `gcc`. Usually an extension is not added for executable files.***

### C Sharp
#### Compile
``` Bash
mcs ./filename.cs
```
#### Run
``` Bash
mono filename.exe
```
***Although the Roslyn compiler outputs a Windows executable, it can also run on Linux systems with the `mono` command.***

# Other Useful Commands
### File permissions
If you get a permission denied error while executing a program, run the following to give all users permission to execute, read and write to the file.

``` Bash
chmod 777 ./filename
```