---
title: "Course Organization"
date: 2022-02-08
description: >
  This article gives a brief description of how the course, *Practical Molecular Dynamics*, is organized.
---

## Introduction

### Course Learning Goals

!!! info

    Each lab will have a set of specific learning outcomes (learning objectives) that will be listed at the beginning of the lab.

### Course Learning Outcomes (Learning Objectives)

## Course Summary

| Part   | Lab      | Topic                               | Date |
| ------ | -------- | ----------------------------------- | ---- |
| Part 1 |          | **Getting Started**                 |      |
|        | Lab 00   | Introduction <br/>and account setup |      |
|        | Lab 01   | Jupyter and Colaboratory            |      |
|        | Lab 02   | analyzing PDB files                 |      |
|        | Lab 03   | NGLView                             |      |
|        | Lab 04   | Plotly                              |      |
|        | Lab 05   | VMD                                 |      |
|        | Lab 05.5 | PyMOL (optional)                    |      |
| Part 2 |          | **MD Simulations**                  |      |
|        | Lab 06   | Introduction to MD                  |      |
|        | Lab 07   | GROMACS tutorial                    |      |
|        | Lab 08   | GROMACS                             |      |
|        | Lab 09   | OpenMM                              |      |
|        | Lab 10   | NAMD and CHARMM                     |      |
| Part 3 |          | **Trajectory Analysis**             |      |
|        | Lab 11   | Introduction to MD analysis         |      |
|        | Lab 12   | RMSD and RMSF                       |      |
|        | Lab 13   | MDAnalysis                          |      |
|        | Lab 14   | MD-Task and `gmx`                   |      |
| Part 4 |          | **Example Publications**            |      |
|        | Lab 15   |                                     |      |

## Course Outline

- Part 1. Getting Started
    - introduction to Jupyter on Colab
    - working with PDB files
        - PDBFixer
        - grep, awk, VSCode
    - viewing protein structures
        - NGLView
        - PyMOL
        - VMD
        - Chimera/ChimeraX (optional) --probably delete this

- Part 2. Molecular Dynamics Simulations
    - introduction
        - simulation programs
            - OpenMM
            - GROMACS
            - Acellera ACEMD
            - AMBER (optional)
            - NAMD (optional)
        - force fields
            - AMBER
            - CHARMM
            - OpenFF
            - CGenFF
            - GAFF2
    - simulations
        - protein simulations
        - ligand-protein simulations
            - docking (Vina/Smina, Dock, MTiOpenScreen)
        - membrane protein simulations (optional)

- Part 3. Trajectory Analysis
    - introduction
    - software tools
        - MDAnalysis- correlationplus
        - GROMACS
        - MD-Task (may not work on colab)
        - MDTraj
        - Bio3D (optional)

    - analyses
        - RMSD, RMSF
        - Ramachandran plot
        - principle component analysis (PCA)
        - residue interaction network (RIN) analysis
        - perturbation response scanning (PRS)
        - dynamic cross-correlation (MD-Task) (may not work on colab)

- Part 4. Example Publications

## Additional Resources

See this course from the summer of 2021, [CHEM 181 Introduction to Molecular Simulation](http://copresearch.pacific.edu/mmccallum/181/index.html).

[CHEM 181 Syllabus](http://copresearch.pacific.edu/mmccallum/181/resources/New-Syllabus.pdf)

The course is set up for 5 weeks.

[bash tutorial](http://www.hypexr.org/bash_tutorial.php#tips)  
[PDBFixer](https://htmlpreview.github.io/?https://github.com/openmm/pdbfixer/blob/master/Manual.html)

### Getting Started Resources

#### The Command Line and Shells

#### Text Editors

- [VS Code](https://code.visualstudio.com/)
- [VS Code on the web](https://vscode.dev/)
- [BBEdit](https://www.barebones.com/products/bbedit/)

#### Graphing with Plotly

- [Plotly Fundamentals](https://plotly.com/python/plotly-fundamentals/)
- [Plotly Tutorials](https://www.geeksforgeeks.org/python-plotly-tutorial/)
- [Jupyter Notebook Tutorial in Python](https://plotly.com/python/ipython-notebook-tutorial/)

## Questions About Protein Structure Validation

See [Structure validation practical - answers](https://www.ebi.ac.uk/pdbe/modval-answers)

## Other Courses

[Molecular Dynamics simulations in Python](https://klyshko.github.io/teaching/2019-03-01-teaching)
[Molecular Modeling Practical](http://cgmartini.nl/~mdcourse/pepmd/analysis.html)

## Docking

Use the webserver below to see if your identified ligand will be modified by a human cytochrome p450.

[https://doi.org/10.1021/acs.jcim.1c00144](https://doi.org/10.1021/acs.jcim.1c00144)

Open Lab.01 IBM 3202  
for preparing protein structure (`pdb`) files with `grep`  

also look at the Cancer Biology PyMOL docking project for multiple examples of `grep`-ping files for fun and profit.  

!!! quote ""

    get `.pdb` file &#8594; ? &#8594; profit!

## Integration with Canvas

See the [IllumiDesk site](https://www.illumidesk.com/) for information.

## Course Notes

Start with GROMACS and OpenMM. Add Amber and NAMD later.

## CUR Possibilities

Use AlphaFold2 and/or I-TASSER to model structures from metagenomes (ocean, human microbiome). Use MD simulations as part of validation.

See ResearchGate: [Is it necessary to run molecular dynamic simulation after modelling of unknown protein structure?](https://www.researchgate.net/post/Is_it_necessary_to_run_molecular_dynamic_simulation_after_modelling_of_unknown_protein_structure)

Structure Refinement

:   GOAP, ModRefine, GalaxyRefine

assess the reliability of predicted model

:   RAMA plots, ProTSAV, SAVES, Molprobity

MD Simulations

:   Stability of protein structure, and RMSD

See [Assessment of ab initio models of protein complexes by molec...](https://www.pnas.org/content/102/19/6679)

Citation: Cheung NJ, Yu W (2018) De novo protein structure prediction using ultra-fast molecular dynamics simulation. PLoS ONE 13(11): e0205819. https://doi.org/10.1371/journal.pone.0205819

### Other Notes

Use [Alphafold 2.0](https://alphafold.ebi.ac.uk/) to get the 3D structure of your protein of interest (whether or not the structure has been solved by other means).

Use the [PASSer 2.0 server](https://passer.smu.edu/) to locate potential allosteric sites for docking.

Dock subsets of the Zinc chemical database using [Gnina](https://github.com/gnina/gnina).

Optional: Use MTiOpenScreen instead

Validate the docking using molecular dynamics simulations.

Analyze simulations with and without inhibitor.

Prepare paper using template
Prepare online slide presentation
(optional: prepare YouTube presentation using template)


AI in Drug Discovery

