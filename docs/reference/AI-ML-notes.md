# AI ML Notes

## Use ML to identify protein-protein interaction interfaces

Mine RCSB for all multimers (including large scale multimers solved by cryo-EM)  
Identify all interacting surfaces  
MD sims of monomers to examine variability of surface  
Use dataset for training a model (save some for tests)  
test model with knowns  
test model with unknowns  

## Use ML to identify PPIIs

Identify interacting surface of a known protein-protein interaction  
MD sims to identify conformers that should not bind  
Identify potential pockets  
Dock small molecules to find those that stabilize the non-binding conformer  

## ML with macromolecules

[PyUUL](https://pyuul.readthedocs.io/install.html) can parse `pdb` files and create objects that can be used with common ML algorithms. Also see [the PyUUL paper](https://pubmed.ncbi.nlm.nih.gov/35181656/).

## other

Use the method outlined in [DOI: 10.1002/prot.26345](https://doi.org/10.1002/prot.26345) on multiple frames of a trajectory to find the largest differences between particular cavities. New cavities could be used for docking.

See [PyUUL for ML](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8857184/#MOESM6)

The authors show how to optimize GTP in binding pocket.

Look for structures of proteins of unknown functions (or others)  
Run some MD sims  
See if you can get this ML to identify ATP or GTP binding pockets in new proteins  
Should be straightforward to test  

Or look for allosteric sites  
Start with NMR structure  
Do short MD sims using each model as a starting point  
find frames in the trajectory that are the most different (largest RMSD, RMSF, Rama)  
identify surface pockets  

## Introduction to ML and DL

[MIT Introduction to Deep Learning | 6.S191](https://www.youtube.com/watch?v=7sB052Pz0sQ)

[Deep Learning Basics | Colab notebook](https://colab.research.google.com/github/lexfridman/mit-deep-learning/blob/master/tutorial_deep_learning_basics/deep_learning_basics.ipynb) This has nice summary Mermaid diagrams of the types of machine learning.

[Google Colab for Machine Learning Projects](https://machinelearningmastery.com/google-colab-for-machine-learning-projects/) This includes a nice introduction to Google Colab. There is also a description of what you need to do to save your partially trained model from the random Colab shutdowns--saving checkpoint files to mounted google drive.




