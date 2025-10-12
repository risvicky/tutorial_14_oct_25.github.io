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

##### Molecular Dynamics (MD) Simulations
Description of the time evolution of chemical systems by propagation the Newton's equations of motion. 
<p align="center">
<img src=/figure/loop.png width="400" height="400">
<img src=/figure/integration.png width="400" height="400">
</p>
![MD simulation workflow](/figure/loop.png)
![Integration of Newton's equations of motion](/figure/integration.png)

#### Energy and Forces
Difference of Molecular Mechanics and Quantum Mechanics

#### Bonded and Non-bonded Interactions



#### Force Fields
![Force Field](/figure/FFs.png)



#### Periodic Boundary Conditions (PBC)
In MD simulation, systems are treated as if they were surrounded by their identical copies in all directions.
<p align="center">
<img src="/figure/pbc_1.png" width="500" height="500"
</p>

If particle A leaves the original box to the right, its corresponding periodic image re-enters through the opposite face.


#### Ensembles
    - Microcanonical Ensemble (NVE)
    - Canonical Ensemble (NVT)
    - Isothermal-Isobaric Ensemble (NPT)

#### Radial Distribution Function (RDF)

