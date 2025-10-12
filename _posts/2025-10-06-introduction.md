---
title: "Introduction to Molecular Dynamics Simulations with GROMACS"
date: 2025-10-06
author: "Risnita Vicky Listyarini"
---

### Chemical Simulations 

##### Why work with computer-aided methods?
The main goal of computer-aided methods in chemistry and material design is to obtain information about chemical system by modeling atoms, molecules and ions on the computer.

##### Advantages of computer-aided methods:
- Cost-effective
- Possibility of studying systems of interest on the atomic level
- Ability to simulate conditions that are difficult to achieve experimentally

#### Energy and Forces
When we perform a simulation of a chemical system, we are interested in the energy and forces acting on the atoms.

The energy of a system is a function of the positions of all atoms in the system. 
The forces acting on each atom are related to the energy by the following equation:

$$ F_i = - \frac{\partial E}{\partial r_i} $$

where $$ F_i $$ is the force acting on atom $$  i $$ , $$  E $$  is the total energy of the system, and $$  r_i $$ is the position of atom $$  i $$.

The level of theory used to calculate the energy and forces determines the accuracy and computational cost of the simulation.

There are two main approaches to calculate the energy and forces: Molecular Mechanics (MM) and Quantum Mechanics (QM).

**Difference of Quantum Mechanics (QM) and Molecular Mechanics (MM)**

| Quantum Mechanics (QM) | Molecular Mechanics (MM)("Force Fields") |
| ----------- | ----------- |
|  Based on numerical solutions of Schrödinger's equation to model the electron density of the system: | Based on parametrised potential functions: |
|$$ \hat{H} \Psi = E \Psi $$ | $$ E_{total} = E_{bonded} + E_{non-bonded} $$ |
|  Accurate but computationally expensive (inclusion of - polarisation, charge-transfer effects, many body effects) | fast computationally (needs parameterisation) |


#### Molecular mechanics (MM)/Force Fields (FFs)
Synonyms: 
- molecular mechanics (MM)
- empirical potentials, potential model
- classical approach, classical treatment, etc.
- but not: Molecular Modelling !

The main idea of MM is to describe molecular interactions via empirical, parametrised potential function.

MM estimates the potential energy of the system by ignoring the electronic motion and considering the positions of nuclei. 

It models atoms as spheres and bonds as springs, and the potential energy of the system is calculated based on the bond stretching, angle bending, dihedral angle interaction, and non-bonded contributions between the
atoms in the system. 

Hooke’s law is typically used to define bond stretching and angle bending. The typical form of FFs (i.e., functional form) to describe the intra- and intermolecular potential energy function of a collection of atoms in the system can be expressed as:

![Force Field](/figure/FFs.png)

where the first four terms represent the bonded interactions (bond stretching, angle bending, dihedral angle torsion, and improper dihedral angle torsion), and the last two terms represent the non-bonded interactions (van der Waals and electrostatic interactions).

The well-known Lennard-Jones potential energy function is employed to describe the van der Waals interaction between two atoms in the system which is given by:
$$ E_{LJ} = 4 \epsilon \left[ \left( \frac{\sigma}{r} \right)^{12} - \left( \frac{\sigma}{r} \right)^{6} \right] $$

where $$  r $$ is the distance between two atoms, $$  \epsilon $$ is the depth of the potential well, and $$  \sigma $$ is the distance at which the potential energy is zero.


##### Molecular Dynamics (MD) Simulations
Description of the time evolution of chemical systems by propagation the Newton's equations of motion. 
![MD simulation workflow](/figure/loop.png){: width="600" height="auto" .center}
![Integration of Newton's equations of motion](/figure/integration.png){: width="300" height="auto" .center}







#### Periodic Boundary Conditions (PBC)
In MD simulation, systems are treated as if they were surrounded by their identical copies in all directions.
![Periodic Boundary Condition](/figure/pbc_1.png){: width="500" height="auto" .center}


A representation of a three-dimensional periodic system. The simulation box is represented
by a cubic box of length *L*. The cubic box is surrounded by its identical copies. **A** particle, marked in
green within the central box, can exit the box through the surface of the box. Upon leaving, its periodic
image will reappear, entering from the opposite side.


#### Ensembles
Microcanonical Ensemble (NVE)

Canonical Ensemble (NVT)

Isothermal-Isobaric Ensemble (NPT)

#### Radial Distribution Function (RDF)

