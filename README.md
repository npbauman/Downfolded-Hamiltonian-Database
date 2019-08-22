# Downfolded Hamiltonian Database

This repository contains a collection of Hamiltonians obtained from the double 
unitary coupled-cluster (DUCC) formalism described in the following paper:

[Nicholas P. Bauman, Eric J. Bylaska, Sriram Krishnamoorthy, Guang Hao Low, 
Nathan Wiebe, and Karol Kowalski. "Downfolding of many-body Hamiltonians using 
active-space models: extension of the sub-system embedding sub-algebras approach 
to unitary coupled cluster formalisms." arXiv preprint arXiv:1902.01553 (2019).]
(https://arxiv.org/abs/1902.01553)

Each subdirectory contains information about the particular downfolding parameters,
energetics from various levels of theory (using bare and transformed/downfolded 
Hamiltonians) for comparison, along with the one- and two-electron integrals. 

Some things to be aware of:
  1. Pay attention to the number of occupied and virtual orbitals in the 
     information about the particular downfolded Hamiltonian. The downfolding can 
     occur for the virtual orbitals, the occupied orbitals, or both, which is 
     important when running posterior calculations.
  2. Be aware of the source of the cluster amplitudes. The DUCC formalism is
     a way of providing unitary Hamiltonians, but in practice, the source of the
     amplitudes that create the unitary ansatz may not be from a unitary 
     coupled-cluster method.
  3. In the information, there will be a nuclear repulsion energy and possibly a 
     value for a 'shift' that may have to be added to/incorporated into any 
     calculation with the downfolded Hamiltonian. 
     
Each subdirectory will contain an NWCHEM input, output, and files for the one- and 
two-electron integrals. The integrals are outputted as either a '.YAML' or 'FCIDUMP'
file. The one-electron integrals are of the core-Hamiltonian type

<img src="https://latex.codecogs.com/svg.latex?\left&space;(&space;i&space;\left&space;|&space;h&space;\right&space;|&space;j&space;\right&space;)&space;=&space;\int&space;d\mathbf{r_{1}}&space;\psi_{i}^{*}(\mathbf{r_{1}})h(\mathbf{r_{1}})\psi_{j}(\mathbf{r_{1}})," title="\left ( i \left | h \right | j \right ) = \int d\mathbf{r_{1}} \psi_{i}^{*}(\mathbf{r_{1}})h(\mathbf{r_{1}})\psi_{j}(\mathbf{r_{1}})," />

while the two-electron integrals are stored using the Mulliken convention

<img src="https://latex.codecogs.com/svg.latex?\left&space;(&space;i&space;j&space;|&space;k&space;l\right&space;)&space;=&space;\int&space;d\mathbf{r_{1}}&space;d\mathbf{r_{2}}&space;\psi_{i}^{*}(\mathbf{r_{1}})\psi_{j}(\mathbf{r_{1}})r_{12}^{-1}\psi_{k}^{*}(\mathbf{r_{2}})\psi_{l}(\mathbf{r_{2}})." title="\left ( i j | k l\right ) = \int d\mathbf{r_{1}} d\mathbf{r_{2}} \psi_{i}^{*}(\mathbf{r_{1}})\psi_{j}(\mathbf{r_{1}})r_{12}^{-1}\psi_{k}^{*}(\mathbf{r_{2}})\psi_{l}(\mathbf{r_{2}})." />

In both cases, the indices correspond to **'spatial'** orbitals. 

# Note About Active Spaces

A simple description of each active space is provided in corresponding directories 
for each molecule and basis set. The active spaces are chosen based on either a 
general molecular orbital diagram or such that there is a significant difference 
in energy between highest(lowest) energy unoccupied(occupied) orbital in the active 
space and the next highest(lowest) energy unoccupied(occupied) orbital outside of 
the active space. The latter argument is important because from a perturbative 
analysis standpoint, if the active-space orbitals are well separated energetically 
from the remaining orbitals, the external amplitudes defining the downfolded Hamiltonian
are better approximated. That is because one can expect that the corresponding perturbative 
denominators are much larger than those used to define excitations within the active space
and which are determined in the diagonalization of the downfolded Hamiltonian. Along with the
choice of active-space, a series of other approximations are used to define the downfolded 
Hamiltonians (descriptions can be found in each directory), but the larger the active space
the closer thee approximate downfolded Hamiltonian is to the exact downfolded Hamiltonian
(i.e. the one that gives the exact FCI value). It is generally best to use the largest active
whenever possible. 
