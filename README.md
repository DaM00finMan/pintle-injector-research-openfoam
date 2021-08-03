# pintle-injector-research-openfoam

The repository for the CFD Simulation case of a liquid fuel pintle-injector rocket engine conducted using the open-source CFD software, OpenFOAM.

# Stability Analysis of a Liquid-Fuel Pintle Injector
Professor: Dr. Pavel Popov

Master's Student: Matthew Coleman

A Master's Program Thesis Project through San Diego State University

Project Start Date: 09/2020

Project Finish Date: TBD

# Dependencies

This project uses the open-source CFD software OpenFOAM-8 in order to solve the case. This code can be found at https://github.com/OpenFOAM/OpenFOAM-8.git.

# How to Run

With OpenFOAM-8 installed and the repository cloned locally onto the system, there are several execuatble files to help manage the case:

**Case Set-Up**

`makeMesh` creates the mesh using blockMesh, as well as sets up the chemistry properties and merges blocks on the mesh.

**Running the Case**

`./Allrun` runs through the *makeMesh* executable followed by running the case using the sprayFoam solver. This version is for serial-execution.

`./Allrun-background` Same as *Allrun* except executes the solver in the background.

`./Allrun-parallel` Parallel-Execution for the solver.

`./Allrun-FERMI_parallel` Parallel-Execution for the solver on the FERMI supercomputer provided by San Diego State University.

`batchScriptSmol144` The batch script used for running the parallel-execution case on FERMI.

**During Execution**

`./followSprayLog` uses *tail* to follow the output of the log.sprayfoam file while the solver is in the background.

`./followFERMI` same as above except follows the output of the FERMI node.

**After Execution**

`./Reconstruct` If ran in parallel, this command with reconstruct the decomposed mesh after the solver has finished.

**Case Clean-Up**

`./Allclean` Deletes time-stamp folders and cleans up the case for running again.
