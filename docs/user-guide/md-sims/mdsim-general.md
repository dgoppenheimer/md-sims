# General Considerations

from [Knapp *et al.*, 2018](https://pubs.acs.org/doi/10.1021/acs.jctc.8b00391#)

>... a good rule of thumb is to perform a minimum of five to 10 replicas.

## Resources

- [Interactive Molecular Dynamics with GROMACS](https://www.mpinat.mpg.de/grubmueller/interactivemd): This runs within VMD.
- [Managing long simulations](https://manual.gromacs.org/documentation/current/user-guide/managing-simulations.html): There is a good section on reproducibility, which should be presented in class.
- [Molecular Dynamics Simulation using Google Colab](https://github.com/TheBiomics/Molecular-Dynamics) This builds GROMACS/NAMD on Colab.
- [Installation of OpenMM on Google Colaboratory](https://github.com/molmod/openmm-tutorial-msbs/blob/master/setup_on_google_colab.md)
- [Biomolecular Simulation: OpenMM and MDAnalysis](https://emleddin.github.io/2020-06-05-py-tutorial/setup.html)
- [Molecular Dynamics simulations in Python](https://klyshko.github.io/teaching/2019-03-01-teaching) This has a nice tutorial on Newton's Laws of Motion, and nice python exercises to illustrate them.
- [Amber in Colab](https://github.com/zj-zhang/AMBER)
- [Running Molecular Dynamics with Amber on Compute Canada](https://computecanada.github.io/molmodsim-amber-md-lesson/aio/index.html) This has a nice set of mermaid diagrams for a MD simulation with AMBER.

## Notes

I would like to use the recently developed `ff19SB` AMBER force field<a name="cite_ref-1"></a>[<sup>[1]</sup>](#cite_note-1)

<mark>NOTE: AMBER22 is not free; the cost is ~$500</mark>.

<a name="cite_note-1"></a>1. Tian C, Kasavajhala K, Belfon KAA, Raguette L, Huang H, Migues AN et al. (2020) ff19SB: Amino-Acid-Specific Protein Backbone Parameters Trained against Quantum Mechanics Energy Surfaces in Solution. *J Chem Theory Comput* **16**: 528-552. [DOI: 10.1021/acs.jctc.9b00591](https://doi.org/10.1021/acs.jctc.9b00591) [&#8617;](#cite_ref-1)
