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

Right-hand click on the MPIHelloWorld.cpp, select Properties and add your local Include Directories.


<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/pictures/settings-include.PNG" width="452">



## Testing the Executable on your local machine 

The executable can be tested like this

```
mpiexec -n 8 MPIHelloWorld.exe
```


<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/pictures/mpirun-windows.PNG" width="452">


## Testing the Executable on your Cloud VM

Open the portal and create a Windows Server
https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal
Upload your executable and run your mpi executable on a single node

## Running Multinode jobs 

please read https://docs.microsoft.com/en-us/azure/batch/batch-mpi for running multinode jobs. Azure Batch is the easiest way 
There are complete samples available
https://github.com/Azure/azure-batch-samples/archive/master.zip



