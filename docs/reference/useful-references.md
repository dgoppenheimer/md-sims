# Useful References

[Machine Learning in Structural Biology](https://www.mlsb.io/#:~:text=Machine%20learning%20also%20shows%20great,learning%20with%20experimental%20structure%20determination.)  
Workshop at the 35th Conference on Neural Information Processing Systems 2021



Ron O. Dror, Robert M. Dirks, J.P. Grossman, Huafeng Xu, and David E. Shaw. "Biomolecular Simulation: A Computational Microscope for Molecular Biology." Annual Review of Biophysics, 41:429-452, 2012. https://doi.org/10.1146/annurev-biophys-042910-155245
 
Avoiding False Positive Conclusions in Molecular Simulation: The Importance of Replicas

Bernhard Knapp, Luis Ospina, and Charlotte M. Deane
Journal of Chemical Theory and Computation 2018 14 (12), 6127-6138
DOI: 10.1021/acs.jctc.8b00391

Bernhard Knapp*Bernhard Knapp

Sobolev OV, Afonine PV, Moriarty NW, Hekkelman ML, Joosten RP, Perrakis A et al. (2020) A Global Ramachandran Score Identifies Protein Structures with Unlikely Stereochemistry. Structure 28: 1249-1258.e2. [DOI: 10.1016/j.str.2020.08.005](https://doi.org/10.1016/j.str.2020.08.005)

## Online Courses

[CHEM 181 Introduction to Molecular Simulation](http://copresearch.pacific.edu/mmccallum/181/index.html)  
This course was last offered in 2020.  
See [course syllabus here](http://copresearch.pacific.edu/mmccallum/181/resources/New-Syllabus.pdf)  
[Data analysis](http://copresearch.pacific.edu/mmccallum/181/styled-6/styled-23/index.html)  

[Molecular Modeling Practical](http://md.chem.rug.nl/~mdcourse/molmod2012/index.html)  
This excellent practical uses an analysis of prion proteins from different sources.  
This practical is from 2012.  
See the [Analysis Section](http://md.chem.rug.nl/~mdcourse/molmod2012/analysis.html) for examples of typical analyses done with GROMACS.  

[PDBe Teaching Materials](https://www.ebi.ac.uk/pdbe/training/teaching-materials)  

Good introductory questions for PDB files can be found at the [Biomolecular Structures and Models (Pre-test) site](https://pdb101.rcsb.org/teach/tests/biomolecular-structures-and-models-pre-test) and the [Biomolecular Structures and Models (Post-test) site](https://pdb101.rcsb.org/teach/tests/biomolecular-structures-and-models-post-test).  

[PHY542: MD analysis with VMD tutorial](https://becksteinlab.physics.asu.edu/pages/courses/2017/PHY542/practicals/md/dynamics/rmsd_fitting.html)

[Running Molecular Dynamics with Amber on Compute Canada](https://computecanada.github.io/molmodsim-amber-md-lesson/aio/index.html)

## Websites

[MolProbity](http://molprobity.biochem.duke.edu/index.php?MolProbSID=1mivhrsmc6ajmk6g8a9i6gskl1&eventID=36)  

To calculate Ramachandran Z-scores: [Tortoize](https://pdb-redo.eu/tortoize)  

!!! note

    To analyze the Z-scores of each frame of a trajectory, you need to download and run Tortoize locally. 

    [Tortoize GitHub repository](https://github.com/PDB-REDO/tortoize)  
    Requirements:
        [libcif++](https://github.com/PDB-REDO/libcifpp)  
        [libzeep](https://github.com/mhekkel/libzeep)

[Running a Simulation in Amber](https://computecanada.github.io/molmodsim-amber-md-lesson/aio/index.html)  
This page shows an excellent flowchart and outline of the steps necessary for preparing the protein structure for simulation using AMBER. It also has a series of exercises that are useful for teaching.

## Integrating Jupyter Notebooks and Canvas

[Illumidesk](https://www.illumidesk.com/)

## Protein structure analysis

[Structure validation practical - answers](https://www.ebi.ac.uk/pdbe/modval-answers)

[PDBe Tutorials](https://www.ebi.ac.uk/pdbe/training/tutorials)  

## Test Mermaid Diagram


``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```
