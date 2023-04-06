Using GROMACS

Most of this information comes from the [GROMACS Tutorial Lysozyme in Water](http://www.mdtutorials.com/gmx/lysozyme/index.html) put together by Justin A. Lemkul, Ph.D.

I'll use human cofilin. NMR structures are available from the RCSB PDB: [1Q8X](https://www.rcsb.org/structure/1Q8X), [1Q8G](https://www.rcsb.org/structure/1Q8G), and a crystal structure, [4BEX](https://www.rcsb.org/structure/4BEX).

Here are tutorials on preparing your structure for MD simulations:

[Preparing Your System for Molecular Dynamics (MD)](https://ctlee.github.io/BioChemCoRe-2018/system-prep/) and [Molecular Dynamics Simulation Tutorial](http://www.bpc.uni-frankfurt.de/guentert/wiki/images/9/96/180618_TutorialMD.pdf).

Points to examine:

1. Are there waters or other solvent molecules present?
2. Are ions or ligands present?
3. Are there any amino acids or loops missing?
    - Check the `.pdb` file in a text editor (VS Code) for entries under `MISSING`.
4. Are any amino acids present as rotomers?
5. Are multiple chains present?

```txt
# Rename "PDB general atom name" to "CHARMM-specific atom name"
#   HIS => HSD (but not included in this protein)
#   CD1 atom of ILE => CD
#   C-terminal carboxyl oxygen O and OXT => OT1 and OT2
[atomselect top "resname HIS"                      ] set resname HSD
[atomselect top "resname ILE and name CD1"         ] set name CD
[atomselect top "chain A and resid 56 and name O"  ] set name OT1
[atomselect top "chain A and resid 56 and name OXT"] set name OT2
```

- proper orientations of glutamine and asparagine amide groups
- protonation state and side chain orientation of histidine residues are consistent
- no other problems exist with the system

The Schrodinger Protein Preparation Wizard enables this increased efficiency in structure preparation by including tools which allow you to:

- Automatically import full PDB files — or any chain within a PDB file — from local databases or the PDB website
- Automatically add missing hydrogen atoms
- Correct metal ionization states to ensure proper formal charge and force field treatment
- Enumerate bond orders to HET groups
- Remove co-crystallized water molecules at the user's discretion
- Cap protein termini with ACE and NMA residues
- Highlight residues with missing atoms or multiple occupancies
- Pre-process structures for Prime, Schrödinger's program for protein structure prediction
- Easily navigate between different residues, HET groups, and chains using intuitive graphical tools
- Quickly and easily determine the most likely ligand protonation state as well as the energy penalties associated with alternate protonation states
- Determine optimal protonation states for histidine residues
- Correct potentially transposed heavy atoms in arginine, glutamine, and histidine side chains
- Optimize the protein's hydrogen bond network by means of a systematic, cluster-based approach, which greatly decreases preparation times


- Alternates. Residues with alternate locations and/or ambiguous sequence identities are examined, and those with the highest occupancy are chosen.
- Termini. Protein chain C- or N-termini that need to be charged or capped require attention. Similarly, for DNA structures the terminal phosphate may only have three oxygen atoms bonded to the phosphorus. Accordingly, an additional oxygen atom should be added.
- Sometimes loops are very disordered and appear as breaks in the chain. It may be possible to use a loop library to model a replacement.
- Hydrogen atoms are usually not visible and so need to be added and checked. In particular, hydrogen atoms on heteroatoms and water molecules should be checked, especially at the active site where the local environment may influence a residue’s pKa value.
- Ligand. Novel ligands in particular need checking to confirm that atoms and bond orders are correct.
- Conformation. Check that torsions are reasonable and there are no clashes.
Charge. The charge on all ionizable groups should be checked.


Although it is often useful to examine the structure using molecular visualization software like [ChimeraX](https://www.rbvi.ucsf.edu/chimerax/) or [PyMOL](https://pymol.org/2/), it is possible to miss some of these things depending on how the software chooses to display them. For example, opening an NMR structure in PyMOL will only display one structure until you `split_chains`. Also, multiple rotamers will not usually be displayed.




---

## Other Resources

[Practical 2: Introduction to protein simulations](https://www3.mpibpc.mpg.de/groups/de_groot/compbio/p2/index.html) provides useful information
