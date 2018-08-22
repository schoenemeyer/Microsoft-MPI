# Microsoft-MPI
How to build MPI Executable for Microsoft OS with Visual Studio 2017


Download MS-MPI SDK

##Installation 

1. Download MS-MPI v9.0.1 

http://go.microsoft.com/FWLink/p/?LinkID=389556

<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/pictures/download-mpi.PNG" width="452">


2. Verify that the MS-MPI environment variables have been set 
 
<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/setmsmpi.PNG" width="452">

2. Install INSTALL VISUAL STUDIO 2017
https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio

3. Download MPIHelloWorld Projekt
https://hpccenth2lts.blob.core.windows.net/windows/MPIHelloWorld.zip

unzip ther file and open the file MPIHelloWorld.sln with Visual Studio


## test 
Install Microsoft HPC-Pack 2012 Client or 2016
Download https://www.microsoft.com/en-us/download/confirmation.aspx?id=36044

Install  HPC Pack 2012 SDK 
Download  HPC Pack 2012 SDK 
https://www.microsoft.com/en-us/download/confirmation.aspx?id=36043


https://blogs.technet.microsoft.com/windowshpc/2015/02/02/how-to-compile-and-run-a-simple-ms-mpi-program/




```

// MPIHelloWorld.cpp: Definiert den Einstiegspunkt für die Konsolenanwendung.
#include "stdafx.h"
#include "stdio.h"
#include "mpi.h"

int main(int argc, char** argv) {
	// Initialize the MPI environment
	MPI_Init(NULL, NULL);

	// Get the number of processes
	int world_size;
	MPI_Comm_size(MPI_COMM_WORLD, &world_size);

	// Get the rank of the process
	int world_rank;
	MPI_Comm_rank(MPI_COMM_WORLD, &world_rank);

	// Get the name of the processor
	char processor_name[MPI_MAX_PROCESSOR_NAME];
	int name_len;
	MPI_Get_processor_name(processor_name, &name_len);

	// Print off a hello world message
	printf("Hello world from processor %s, rank %d out of %d processors\n",
		processor_name, world_rank, world_size);
	// Finalize the MPI environment.
	MPI_Finalize();
}



```

## Testing



<img src="https://github.com/schoenemeyer/Microsoft-MPI/blob/master/pictures/mpirun-windows.PNG" width="452">
