# AMUSEingBlackHole

### A N-body cosmological simulation code to study the formation of Supermassive Black Hole seeds in dense stellar cluster.

##### This is the official repository for AMUSEingBlackHole. AMUSEingBlackHole is a N-body code written in Python 3.0 that is able to simulate dense stellar clusters with many star particles. It is super fast and could use a single CPU, CPU cluster, GPU and GPU cluster as per requirement.

---

#### Key feautres:

1. Accretion recipes: Different accretion recipes e.g., constant accretion, **Bondi-hoyle-lyttleton** accretion and **Eddington** accretion
2. Mass-radii relationship for main sequence stars 
3. Collisions are handled by sticky sphere approximation 
4. Gravitational interactions between the stars are modelled using the N-body code ph4
5. Gravitational effect of the gas cloud is included via an analytical background potential coupled to the N-body code using the BRIDGE method
6. A salpeter IMF for the initial mass function. 
7. All the outputs are saved in Pandas Dataframe. HDF5 is also possible.

--- 

#### Powered by: 

* Numpy
* scipy
* astropy
* pandas
* matplotlib
* mpi4py
* cuda 

--- 

The detailed physics in this code could be found in [this paper](https://ui.adsabs.harvard.edu/abs/2021MNRAS.503.1051D/abstract).

---

### Basic Usage

AMUSEingBlackHole is written in Python 3.0. The installation guide for Python 3.0 could be found [here](https://www.python.org/download/releases/3.0/). The code can also be run with Python 2.0, but the print statements need to be modified. The code is powered by Astrophysical Multipurpose Software Environment a.k.a AMUSE. The installation guide and documentation for AMUSE could be found [here](https://amusecode.github.io/). Once Python, AMUSe and all other packages are installed the code can simply be run using
```
python AMUSEingBlackHole.py 
```
or by using
```
..directory_to_amuse/amuse.sh AMUSEingBlackHole.py
```
The code can also be run in parallel using 
```
mpiexec python AMUSEingBlackHole.py
```
In order to switch between CPU and GPU modify the following line in the original code
```python 
grav = ph4(converter,mode='gpu')
```
The code can also use multiple CPU or GPU. For example, to run the code using a cluster of 8 gpus, add the arguement *number_of_workers* to the following line 
```python
grav = ph4(converter,number_of_workers=8, mode='gpu')
```
