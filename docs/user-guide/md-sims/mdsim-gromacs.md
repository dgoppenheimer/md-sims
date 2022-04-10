# Molecular Dynamics Simulations with GROMACS

These instructions were largely adapted from [Installing Software on Google Colab for IBM3202 tutorials](https://colab.research.google.com/github/pb3lab/ibm3202/blob/master/tutorials/lab00_software.ipynb). I updated the GROMACS version, and to do that I needed to upgrade `cmake`.

<mark>Installation of this software takes about 40 min.</mark> Therefore, we will save the compiled software on Google Drive to save time later.

<mark>**VERY IMPORTANT FIRST STEP:**</mark> Go to the Menu &#8594; *Runtime* &#8594; *Change Runtime Type* and choose GPU!

**Note:** a page reload will be required. This is okay.

First, let's confirm that we are in the correct directory.

```py
!pwd
/content
```













## Resources

- [Interactive Molecular Dynamics with GROMACS](https://www.mpinat.mpg.de/grubmueller/interactivemd): This runs within VMD.
- [Managing long simulations](https://manual.gromacs.org/documentation/current/user-guide/managing-simulations.html): There is a good section on reproducibility, which should be presented in class.



## Trp-cage

2jof

[The tryptophan-cage (Trp-cage) is a stability (*sic*) folded mini protein](https://www.biosyn.com/tew/The-tryptophan-cage-(Trp-cage)-is-a-stability-folded-mini-protein.aspx)