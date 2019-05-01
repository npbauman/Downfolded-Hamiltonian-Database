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
     amplitudes that create the unitary ansatz may not be from a unitary coupled-
     cluster method.
     
