# Exploring and Modifying `.pdb` Files

## Formative Assessments

70-80%

- questions during exercise
- also provide practice exams--relatively easy to provide pdb files to play with

## Summative Assessments

20-30%

- higher stakes
- should have a (generous) time limit
- can I grade these pdb file manipulations by diff?
- open book (internet)?

## Fixing Missing Loops

### Web Servers for Fixing Missing Loops

### CLI Programs for Fixing Missing Loops

### Additional Information about Fixing Missing Loops

## Adding Hydrogens

### Web Servers for Adding Hydrogens

The [MolProbity](http://molprobity.biochem.duke.edu/) webserver is excellent for assigning hydrogens to structures and providing a measure of how accurate the resulting model is including identifying rotamers, etc.

The [What If](https://swift.cmbi.umcn.nl/servers/html/index.html) webserver can assign hydrogens to heavy atoms and optimize the H-bonding network.

### CLI Programs for Adding Hydrogens

[gmx pdb2gmx](https://manual.gromacs.org/documentation/current/onlinehelp/gmx-pdb2gmx.html) is part of the GROMACS installation and can be used in Jupyter Notebooks. It is powerful and has sensible defaults. It is probably worth using it on a protein structure file and running the result through MolProbity.

The command line program [Reduce](https://github.com/rlabduke/reduce) can be used to add hydrogens to protein structures. This is the program that is used on the MolProbity website. See more at the [Reduce Overview](http://molprobity.biochem.duke.edu/help/reduce_guide/reduce_guide.html) web site.

[PDBFixer](https://github.com/openmm/pdbfixer) is part of the OpenMM suite of programs.

[Open Babel](http://openbabel.org/wiki/Main_Page) can be used to add polar hydrogens to protein structures using the command line. This could be potentially used within a Jupyter Notebook, but I need to check on how decisions about hydrogen additions are made.

[UCSF Chimera](https://www.cgl.ucsf.edu/chimera/) is a full service molecular graphics program that can add hydrogens and can fix atypical amino acids (using DockPrep).

### Additional Information about Adding Hydrogens

The Protopedia webpage on [Hydrogen in macromolecular models](https://proteopedia.org/wiki/index.php/Hydrogen_in_macromolecular_models) has a nice introduction to hydrogens in protein structures.

## Additional Reading

[Introduction to PDB Data](https://pdb101.rcsb.org/learn/guide-to-understanding-pdb-data/introduction)

[Introduction to Protein Data Bank Format](https://www.cgl.ucsf.edu/chimera/docs/UsersGuide/tutorials/pdbintro.html)

[Protein Structure Analysis: Extra Information in a Protein Data Bank File](https://bitesizebio.com/61389/protein-data-bank-files/) Good information about how to parse a pdb file, and how to calculate a B-factor.

[Atomic Coordinate Entry Format Version 3.3](https://www.wwpdb.org/documentation/file-format-content/format33/sect9.html) from the World Wide Protein Data Bank website. This has an excellent explanation of the format of `.pdb` files.

Also see [Atomic Coordinate Entry Format Version 3.3](https://www.wwpdb.org/documentation/file-format-content/format33/v3.3.html)
