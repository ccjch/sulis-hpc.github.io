# LAMMPS Acceleration Package Benchmarks on Sulis

## Overview

Nine LAMMPS potential benchmark cases were run for each of four acceleration package choices. For each benchmark case the results have been graphed to show the relative performance when using the four acceleration packages.

The results shown are the average over three runs.

## Benchmark Cases

* **in.intel.airebo** - AIREBO polyethelene benchmark
* **in.intel.dpd** - Dissipative Particle Dynamics 
* **in.intel.eam** - Embedded Atom Method, copper lattice 
* **in.intel.lc** - Liquid crystal, Gay-Berne potential 
* **in.intel.lj** - Atomic fluid, Lennard-Jones potential 
* **in.intel.rhodo** - Rhodopsin model
* **in.intel.sw** - Silicon with Stillinger-Weber
* **in.intel.tersoff** - Silicon with Tersoff 
* **in.intel.water** - Coarse-grain water simulation using Stillinger-Weber


## Acceleration Packages

* **ref** - default MPI implementation
* **intel** - the Intel acceleration package
* **openmp** - the OpenMP acceleration package
* **kokkos** - the Kokkos acceleration package

In some cases the potential is not supported by one or more of the packages.

Sulis uses AMD CPUs, so the intel package has been built with gcc. As a result of using gcc some of its optimisations are automatically disabled.


## Benchmark Results

For these tests LAMMPS 3Nov2022 was used, running on Sulis' standard compute nodes (128 core).

 

### AIREBO

Performance for a 522240 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/airebo.png" width="600" height="450" alt="Performance graph. Intel provides around a seventy percent advantage.">](./img/airebo.png)

### DPD

Performance for a 512000 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/dpd.png" width="600" height="450" alt="Performance graph. Intel underperforms the others by around 20 percent.">](./img/dpd.png)

### EAM

Performance for a 512000 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/eam.png" width="600" height="450" alt="Performance graph.">](./img/eam.png)

### LC

Performance for a 524288 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/lc.png" width="600" height="450" alt="Performance graph. Intel provides almost double the performance.">](./img/lc.png)


### LJ

Performance for a 512000 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/lj.png" width="600" height="450" alt="Performance graph.">](./img/lj.png)

### RHODO

Performance for a 512000 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/rhodo.png" width="600" height="450" alt="Performance graph.">](./img/rhodo.png)

### SW

Performance for a 512000 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/sw.png" width="600" height="450" alt="Performance graph.">](./img/sw.png)

### TERSOFF

Performance for a 512000 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/tersoff.png" width="600" height="450" alt="Performance graph. Kokkos provides around a ten percent advantage.">](./img/tersoff.png)

### WATER

Performance for a 512000 atom system, on 1 to 8 nodes. Click on the picture for a larger version.
[<img src="./img/water.png" width="600" height="450" alt="Performance graph.">](./img/water.png)


## Multi-threaded Results

Not shown in the graphs, we also ran these benchmarks with 1, 2, 4, 8 and 16 threads per MPI task and correspondingly fewer MPI tasks per node, e.g. 32 MPI tasks per node and 8 threads per MPI task.

Getting the threading choice right can often provide a five percent improvement in performance relative to the single-threaded case, so it is well worth benchmarking your problem on your intended number of compute nodes using 1, 2 or 4 threads.

## Credits
 Contributed by Loughborough University


