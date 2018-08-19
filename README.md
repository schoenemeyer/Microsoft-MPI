# Microsoft-MPI
How to build MPI Executable for Microsoft OS with Visual Studio 2017

MS-MPI downloads
The following are current downloads for MS-MPI:

MS-MPI v9.0.1 (new!) - see Release notes
Debugger for MS-MPI Applications with HPC Pack 2012 R2
Earlier versions of MS-MPI are available from the Microsoft Download Center.

# 
Install Microsoft HPC-Pack 2012 Client or 2016
Download https://www.microsoft.com/en-us/download/confirmation.aspx?id=36044

Install  HPC Pack 2012 SDK 
Download  HPC Pack 2012 SDK 
https://www.microsoft.com/en-us/download/confirmation.aspx?id=36043

Install Microsoft MPI SDK
https://msdn.microsoft.com/en-us/library/bb524831.aspx

More Details
https://msdn.microsoft.com/en-us/library/bb524831(v=vs.85).aspx



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

