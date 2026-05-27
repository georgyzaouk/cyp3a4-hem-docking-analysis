# CYP3A4-HEM Docking Analysis

Molecular docking analysis of human Cytochrome P450 3A4 in complex with Protoporphyrin IX containing Fe (HEM), using the protein structure PDB ID: 1W0E.

This project was completed as part of the Computational Biology course at the Lebanese American University.

## Overview

Cytochrome P450 3A4 (CYP3A4) is an important enzyme involved in drug metabolism and detoxification. This project investigates the interaction between CYP3A4 and its HEM ligand through molecular docking and structural analysis.

Docking simulations were performed using AutoDock and AutoDock Vina, while Chimera was used for molecular visualization, structure alignment, and interaction analysis.

## Tools Used

- AutoDock Tools 1.5.7
- AutoDock 4
- AutoDock Vina
- UCSF Chimera 1.18

## Docking Parameters

The docking grid was configured to cover the receptor binding site and ligand position.

- Grid dimensions: 50 × 50 × 50 points
- Grid center: 58.562, 77.922, 14.185
- Grid spacing: 0.375 Å
- Ligand torsional degrees of freedom: 8
- Atom types considered: A, C, Fe, OA, and N

## Key Results

### AutoDock

- Best estimated free energy of binding: -20.36 kcal/mol
- Best docking run: run #66
- Final intermolecular energy: -22.75 kcal/mol
- Torsional free energy: +2.39 kcal/mol
- RMSD tolerance of 2.0 Å: one main cluster across 100 runs
- RMSD tolerance of 1.0 Å: seven clusters

### AutoDock Vina

AutoDock Vina was used to compare and validate the docking results.

| Model | Affinity (kcal/mol) | RMSD l.b. | RMSD u.b. |
|---|---:|---:|---:|
| 1 | -13.5 | 0.000 | 0.000 |
| 2 | -13.4 | 0.355 | 6.267 |
| 3 | -10.7 | 1.232 | 1.484 |

Model 2 showed the closest alignment to the experimental structure, with an RMSD of 0.535 Å over 43 atom pairs.

## Interaction Analysis

The top-docked HEM pose showed stable positioning within the CYP3A4 binding pocket. The interaction analysis identified hydrogen bonding interactions involving residues such as:

- ARG105
- TRP126
- ARG130
- ARG375
- ARG440

These interactions help stabilize the ligand within the binding pocket and support the reliability of the docking pose.

## Repository Structure

```text
cyp3a4-hem-docking-analysis/
├── README.md
├── report/
│   └── docking-analysis-cyp3a4-hem.pdf
├── data/
│   ├── receptor/
│   │   ├── 1w0e_original.pdb
│   │   ├── 1w0e.pdb
│   │   └── 1w0e.pdbqt
│   └── ligand/
│       ├── HEM.pdb
│       └── HEM.pdbqt
├── autodock/
│   ├── HEM.dpf
│   ├── HEM.dlg
│   ├── 1w0e.gpf
│   ├── 1w0e.glg
│   └── maps/
├── vina/
│   ├── config.txt
│   └── HEM_out.pdbqt
└── chimera/
    ├── DockingOutput.conf
    ├── DockingOutput.ligand.pdb
    ├── DockingOutput.ligand.pdbqt
    ├── DockingOutput.receptor.pdb
    └── DockingOutput.receptor.pdbqt
