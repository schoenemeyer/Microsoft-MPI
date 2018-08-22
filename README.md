# Build MPI Codes with Microsoft-MPI

This lab shows step-by-step how to build MPI Executable for Microsoft HPC Server with Visual Studio 2017

## Basic Installation 
 
1. Download MS-MPI v9.0.1 

http://go.microsoft.com/FWLink/p/?LinkID=389556

<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/pictures/download-mpi.PNG" width="452">


2. Verify that the MS-MPI environment variables have been set 
 
<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/setmsmpi.PNG" width="452">

2. Install  VISUAL STUDIO 2017
https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio

Make sure to install the C++ package.

3. Download the MPIHelloWorld Project Folder 
https://hpccenth2lts.blob.core.windows.net/windows/MPIHelloWorld.zip

unzip the file and open the file MPIHelloWorld.sln with Visual Studio 2017. 
Change to the file MPIHelloWorld.cpp. You should see something like this 

<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/pictures/mpihelloworldcpp.PNG" width="452">

## Build the Executable

Right-hand click on the MPIHelloWorld.cpp  and modify 


## Testing the Executable

The executable can be tested
'''
mpiexec -n 2 MPIHelloWorld.exe
'''
<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/pictures/mpirun-windows.PNG" width="452">
