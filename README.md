# Downfolded-Hamiltonian-Database

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
  2. Be aware of the source of the cluster amplitudes. The DUCC formalism is a 
     a way of providing unitary Hamlitonians, but in practice the source of the
     amplitudes that create the unitary ansatz may not be from a unitary 
     coupled-cluster method.
  3. In the information there will be a nuclear repulsion energy and possibly a 
     value for a 'shift' that may have to be added to/incorporated into any 
     calculation with the downfolded Hamltonian. 
     
Each subdirectory will contain a NWCHEM input, output, and files for the one- and 
two-electron integrals. The integrals are outputted as either a '.YAML' or 'FCIDUMP'
file. The one-electron integrals are of the core-Hamiltonian type:

<img src="https://latex.codecogs.com/gif.download?%5Cleft%20%28%20i%20%5Cleft%20%7C%20h%20%5Cright%20%7C%20j%20%5Cright%20%29%20%3D%20%5Cint%20d%5Cmathbf%7Br_%7B1%7D%7D%20%5Cpsi_%7Bi%7D%5E%7B*%7D%28%5Cmathbf%7Br_%7B1%7D%7D%29h%28%5Cmathbf%7Br_%7B1%7D%7D%29%5Cpsi_%7Bj%7D%28%5Cmathbf%7Br_%7B1%7D%7D%29" />
