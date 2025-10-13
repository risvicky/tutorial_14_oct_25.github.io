---
title: "Introduction to Molecular Dynamics Simulations"
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
When we perform a simulation of a chemical system, we are interested in the **energy** and **forces** acting on the atoms. The energy of a system is a function of the positions of all atoms in the system. 

The forces acting on each atom are related to the energy by the following equation:

$$ F_i = - \frac{\partial E}{\partial r_i} $$

where $$ F_i $$ is the force acting on atom $$ i $$ , $$ E $$ is the total energy of the system, and $$ r_i $$ is the position of atom $$ i $$.

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
- classical approach, classical treatment
- but not: *Molecular Modelling*!

The main idea of MM is to describe molecular interactions via empirical, parametrised potential function.

MM estimates the potential energy of the system by ignoring the electronic motion and considering the positions of nuclei. 

It models atoms as *spheres* and bonds as *springs*, and the potential energy of the system is calculated based on the **bond stretching**, **angle bending**, **dihedral angle** interaction, and **non-bonded** contributions between the atoms in the system. 

**Hooke’s law** (https://en.wikipedia.org/wiki/Hooke%27s_law) is typically used to define bond stretching and angle bending. The typical form of FFs (i.e., functional form) to describe the intra- and intermolecular potential energy function of a collection of atoms in the system can be expressed as:

![Force Field](/figure/FFs.png)

where the first four terms represent the bonded interactions (bond stretching, angle bending, dihedral angle torsion, and improper dihedral angle torsion), and the last two terms represent the non-bonded interactions (van der Waals and electrostatic interactions).

The well-known **Lennard-Jones** (https://en.wikipedia.org/wiki/Lennard-Jones_potential) potential energy function is employed to describe the van der Waals interaction between two atoms in the system which is given by:

$$ E_{LJ} = 4 \epsilon \left[ \left( \frac{\sigma}{r} \right)^{12} - \left( \frac{\sigma}{r} \right)^{6} \right] $$

where $$  r $$ is the distance between two atoms, $$  \epsilon $$ is the depth of the potential well, and $$  \sigma $$ is the distance at which the potential energy is zero.


##### Molecular Dynamics (MD) Simulations
Description of the time evolution of chemical systems by propagation the Newton's equations of motion. 
![MD simulation workflow](/figure/loop.png){: width="600" height="auto" .center}
![Integration of Newton's equations of motion](/figure/integration.png){: width="300" height="auto" .center}



#### Periodic Boundary Conditions (PBC)
In MD simulation, systems are treated as if they were surrounded by their identical copies in all directions.
![Periodic Boundary Condition](/figure/pbc_1.png){: width="500" height="auto" .center}


A representation of a three-dimensional periodic system. The simulation box is represented by a cubic box of length *L*. The cubic box is surrounded by its identical copies. **A** particle, marked in green within the central box, can exit the box through the surface of the box. Upon leaving, its periodic image will reappear, entering from the opposite side.

This approach also considers the **minimum image convention**, which means that each particle only interacts with the nearest image of every other particle (either the original particle or one of its periodic images).

#### Temperature and Pressure Scaling
Molecular dynamics simulations can be carried out using several conditions or ensembles. It requires the use of algorithms that generate a thermodynamic ensemble at constant temperatures known as **thermostats**.

The idea of using thermostats in MD simulation can be for several reasons, e.g., to match with experimental conditions, to make a conformational search faster, or to investigate temperature-dependent processes.

Different types of ensembles can describe the system in molecular dynamics, including the microcanonical, canonical, and isothermal-isobaric ensembles.

**Microcanonical Ensemble (NVE)** describes a system where the number of particles, volume, and energy are constant, representing an isolated system without the exchange of particles or energy with its surroundings.

**Canonical Ensemble (NVT)** applies to a system maintaining constant numbers of particles, volume, and temperature. It acts as a closed system in thermal equilibrium with a heat bath at a constant temperature *T*, allowing for energy exchange.

**Isothermal-Isobaric Ensemble (NPT)** defines a system with a constant number of particles, pressure and temperature. It depicts the system in contact with a heat bath at constant temperature *T* and pressure *P*, capable of exchanging energy and volume with the system. At thermal equilibrium, the total energy *E* and volume *V* fluctuate, whereas the number of particles *N* remains constant.

#### Radial Distribution Function (RDF)/Pair Distribution
The radial distribution function, g(r), describes the number of atoms in a shell $$ \Delta r $$ at a distance *r* from a central species/atom.
It provides information about the structure of liquids and amorphous solids by describing how particle density varies as a function of distance from a reference particle.

![RDF](/figure/GC.png){: width="auto" height="auto" .center}

The RDF depicted in the figure above represents the probablity to find a solvent molecule *j* at a spesific distance *r* from a central solute molecule *i*. 

