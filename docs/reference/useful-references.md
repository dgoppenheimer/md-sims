# Useful References

[Machine Learning in Structural Biology](https://www.mlsb.io/#:~:text=Machine%20learning%20also%20shows%20great,learning%20with%20experimental%20structure%20determination.)  
Workshop at the 35th Conference on Neural Information Processing Systems 2021

Ron O. Dror, Robert M. Dirks, J.P. Grossman, Huafeng Xu, and David E. Shaw. "Biomolecular Simulation: A Computational Microscope for Molecular Biology." Annual Review of Biophysics, 41:429-452, 2012. https://doi.org/10.1146/annurev-biophys-042910-155245

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

[T019 · Molecular dynamics simulation](https://colab.research.google.com/github/volkamerlab/teachopencadd/blob/1bd7cb0c9f6379aebc0c1a0b1c7413685910cffa/teachopencadd/talktorials/019_md_simulation/talktorial.ipynb) Here the authors use OpenMM to simulate a protein-ligand complex. Also a nice introduction to the theory behind molecular dynamics simulations. There are some nice quiz questions and short activities here, too.

[Molecular Dynamics simulations in Python](https://klyshko.github.io/teaching/2019-03-01-teaching) and [Lecture 7: Molecular Dynamics Simulations in Python](https://github.com/klyshko/md_python/blob/master/Lecture.ipynb) both have a nice introduction to the theory behind the simulations. I may not go into this much detail as my current math skills are not up to it.

[QM/MM with GROMACS + CP2K](https://www.archer2.ac.uk/training/courses/220000-gromacs-self-service/)  
One in a series of courses using the Archer2 computing resources in the UK. Learning Outcomes, prerequisites, and requirements are listed. This is a self-service course that is always open.

Also see [QM/MM simulation with GROMACS + CP2K](https://www.archer2.ac.uk/training/courses/210422-gromacs/)

## Tutorials

Here is a Jupyter Notebook in Colab [Tutorial: a simple simulation of alanine dipeptide with ANI-2x using OpenMM-Torch and NNPOps](https://colab.research.google.com/github/openmm/openmm-torch/blob/master/tutorials/openmm-torch-nnpops.ipynb)



## Websites

[MolProbity](http://molprobity.biochem.duke.edu/index.php?MolProbSID=1mivhrsmc6ajmk6g8a9i6gskl1&eventID=36)  

To calculate Ramachandran Z-scores: [Tortoize](https://pdb-redo.eu/tortoize)  

!!! note

    To analyze the Z-scores of each frame of a trajectory, you need to download and run Tortoize locally. 

    [Tortoize GitHub repository](https://github.com/PDB-REDO/tortoize)  
        [libcif++](https://github.com/PDB-REDO/libcifpp)  
        [libzeep](https://github.com/mhekkel/libzeep)

[Running a Simulation in Amber](https://computecanada.github.io/molmodsim-amber-md-lesson/aio/index.html)  
This page shows an excellent flowchart and outline of the steps necessary for preparing the protein structure for simulation using AMBER. It also has a series of exercises that are useful for teaching.

[CP2K Open Source Molecular Dynamics](https://www.cp2k.org/about)  
>CP2K is a quantum chemistry and solid state physics software package that can perform atomistic simulations of solid state, liquid, molecular, periodic, material, crystal, and biological systems.

[Computational Biology Services - Tutorials](https://www.computabio.com/tutorials.html)

[OpenMM User Guide](http://docs.openmm.org/latest/userguide/application/01_getting_started.html)

### ACEMD

[ACEMD: Molecular Dynamics Made Simple](https://www.acellera.com/acemd/) and the accompanying PlayMolecule and HTMD.

### PLUMED

[Master ISDD tutorial 2020: Brief introduction to PLUMED](https://www.plumed.org/doc-v2.6/user-doc/html/master-_i_s_d_d-1.html)

>It can be used to analyze features of the dynamics on-the-fly or to perform a wide variety of free energy methods.

### NNPOps

[NNPOps](https://github.com/openmm/NNPOps)

Part of OpenMM

>The goal of this project is to promote the use of neural network potentials (NNPs) by providing highly optimized, open source implementations of bottleneck operations that appear in popular potentials.
>...
>This code is designed for inference (running simulations)

Jupyter Notebook tutorial:

[Tutorial: a simple simulation of alanine dipeptide with ANI-2x using OpenMM-Torch and NNPOps](https://colab.research.google.com/github/openmm/openmm-torch/blob/master/tutorials/openmm-torch-nnpops.ipynb#scrollTo=oRr7FSA13_Wv)

## Training your own models

[Welcome to TorchANI’s documentation!](https://aiqm.github.io/torchani/)

## Integrating Jupyter Notebooks and Canvas

[Illumidesk](https://www.illumidesk.com/)

## Protein structure analysis

[Structure validation practical - answers](https://www.ebi.ac.uk/pdbe/modval-answers)

[PDBe Tutorials](https://www.ebi.ac.uk/pdbe/training/tutorials)  

## Readings

Hollingsworth SA & Dror RO (2018) Molecular Dynamics Simulation for All. *Neuron* **99**: 1129-1143. DOI: [10.1016/j.neuron.2018.08.011](https://doi.org/10.1016/j.neuron.2018.08.011)

Chen YC (2015) Beware of docking. *Trends Pharmacol Sci* **36**: 78-95. [DOI: 10.1016/j.tips.2014.12.001](https://doi.org/10.1016/j.tips.2014.12.001)

Gapsys V & de Groot BL (2020) On the importance of statistics in molecular simulations for thermodynamics, kinetics and simulation box size. *Elife* **9**: e57589. [DOI: 10.7554/eLife.57589](https://doi.org/10.7554/eLife.57589)

Knapp B, Ospina L & Deane CM (2018) Avoiding False Positive Conclusions in Molecular Simulation: The Importance of Replicas. *J Chem Theory Comput* **14**: 6127-6138. [DOI: 10.1021/acs.jctc.8b00391](https://doi.org/10.1021/acs.jctc.8b00391)

[How to (not) perform a Molecular Dynamics simulation study](https://www.stats.ox.ac.uk/~knapp/paperVersionOfPost_2014.pdf) A good article showing why you should not base conclusions on single MD simulations.

Bruzzese A, Dalton JAR & Giraldo J (2020) Statistics for the analysis of molecular dynamics simulations: providing P values for agonist-dependent GPCR activation. *Sci Rep* **10**: 19942. DOI: [10.1038/s41598-020-77072-4](https://doi.org/10.1038/s41598-020-77072-4)

Yu H & Dalby PA (2020) A beginner’s guide to molecular dynamics simulations and the identification of cross-correlation networks for enzyme engineering. *Methods Enzymol* **643**: 15-49. [DOI: 10.1016/bs.mie.2020.04.020](https://doi.org/10.1016/bs.mie.2020.04.020). This article includes a GROMACS tutorial.

Hildebrand PW, Rose AS & Tiemann JKS (2019) Bringing Molecular Dynamics Simulation Data into View. *Trends Biochem Sci* **44**: 902-913. DOI: [10.1016/j.tibs.2019.06.004](https://doi.org/10.1016/j.tibs.2019.06.004)

Tekpinar M, Neron B & Delarue M (2021) Extracting Dynamical Correlations and Identifying Key Residues for Allosteric Communication in Proteins by correlationplus. *J Chem Inf Model* **61**: 4832-4838. DOI: [10.1021/acs.jcim.1c00742](https://doi.org/10.1021/acs.jcim.1c00742) This is a useful python package to carry out and visualize pairwise correlations in molecular dynamics trajectories.

Sheik Amamuddy O, Veldman W, Manyumwa C, Khairallah A, Agajanian S, Oluyemi O et al. (2020) Integrated Computational Approaches and Tools for Allosteric Drug Discovery. *Int J Mol Sci* **21**: E847. DOI: [10.3390/ijms21030847](https://doi.org/10.3390/ijms21030847)

Metehan Ilter, Ramazan Kasmer, Farzaneh Jalalypour, Canan Atilgan, Ozan Topcu, Nihal Karakas, Ozge Sensoy (2022) Inhibition of mutant RAS-RAF interaction by mimicking structural and dynamic properties of phosphorylated RAS eLife 11:e79747 DOI: [10.7554/eLife.79747](https://elifesciences.org/articles/79747). This may be a good required reading for the course.

Sunseri J & Koes DR (2021) Virtual Screening with Gnina 1.0. Molecules 26: 7369. DOI: [10.3390/molecules26237369](https://doi.org/10.3390/molecules26237369)

## Test Mermaid Diagram

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```

This flowchart was adapted from [Information flow in AMBER](https://computecanada.github.io/molmodsim-amber-md-lesson/aio/index.html)

``` mermaid
graph TD
    A(PDB files)  -->|atom coordinates| B{tLEaP};
    C("Force Field (ff) files") -->|ff parameters| B{tLEaP};
    D(LEaP commands) -->|build system| B{tLEaP};

```
