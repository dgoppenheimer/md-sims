Notes from [ff19SB: Amino-Acid-Specific Protein Backbone Parameters Trained against Quantum Mechanics Energy Surfaces in Solution](https://pubs.acs.org/doi/10.1021/acs.jctc.9b00591)[^1]

>Of the explicit water models tested here, we recommend use of OPC with ff19SB.

From the [GROMACS user manual](https://manual.gromacs.org/documentation/current/user-guide/force-fields.html#:~:text=GROMACS%20supports%20the%20GROMOS%20force,(non%2Dpolar)%20hydrogens.)

>GROMACS versions higher than 4.5 support the following AMBER force fields natively:

>- AMBER94  
>- AMBER96  
>- AMBER99  
>- AMBER99SB  
>- AMBER99SB-ILDN  
>- AMBER03  
>- AMBERGS

>GROMACS supports the GROMOS force fields, with all parameters provided in the distribution for 43a1, 43a2, 45a3, 53a5, 53a6 and 54a7. The GROMOS force fields are united atom force fields, i.e. without explicit aliphatic (non-polar) hydrogens.
>...
>GROMOS 43a1p - 43a1 modified to contain SEP (phosphoserine), TPO (phosphothreonine), and PTR (phosphotyrosine) (all PO42- forms), and SEPH, TPOH, PTRH (PO4H- forms).


OpenMM does not support the Amber ff19SB protein force field.



[^1]: Tian C, Kasavajhala K, Belfon KAA, Raguette L, Huang H, Migues AN et al. (2020) ff19SB: Amino-Acid-Specific Protein Backbone Parameters Trained against Quantum Mechanics Energy Surfaces in Solution. J Chem Theory Comput 16: 528-552. [DOI: 10.1021/acs.jctc.9b00591](https://doi.org/10.1021/acs.jctc.9b00591)