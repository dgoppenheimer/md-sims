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

Open Lab.01 IBM 3202  
for preparing protein structure (`pdb`) files with `grep`  

also look at the Cancer Biology PyMOL docking project for multiple examples of `grep`-ping files for fun and profit.  

!!! quote ""

    get `.pdb` file &#8594; ? &#8594; profit!

## Integration with Canvas

See the [IllumiDesk site](https://www.illumidesk.com/) for information.

## Course Notes

Start with GROMACS and OpenMM. Add Amber and NAMD later.

