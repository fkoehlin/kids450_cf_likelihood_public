This repository contains the likelihood module for the KiDS-450 correlation function measurements from [Hildebrandt et al. 2017 (MNRAS, 465, 1454)](http://adsabs.harvard.edu/abs/2017MNRAS.465.1454H). Note that this is NOT the original likelihood used for their analysis. However, this likelihood was used for the analysis of [Köhlinger et al. 2019 (arXiv:1809.01406)](http://adsabs.harvard.edu/abs/2018arXiv180901406K) and differences with respect to the original CosmoMC likelihood were found to be negligible (please refer to Section 4.1 in [Köhlinger et al. 2019 (arXiv:1809.01406)](http://adsabs.harvard.edu/abs/2018arXiv180901406K) for details). 
The module will be working 'out-of-the-box' within a [MontePython](https://github.com/brinckmann/montepython_public) and [CLASS](https://github.com/lesgourg/class_public) (version >= 2.6!) setup. The required data files can be downloaded from 'http://kids.strw.leidenuniv.nl/sciencedata.php' and the parameter file for reproducing the fiducial run of [Köhlinger et al. 2019 (arXiv:1809.01406)](http://adsabs.harvard.edu/abs/2018arXiv180901406K) is supplied in the subfolder `INPUT` within this repository. 

Assuming that MontePython (with CLASS version >= 2.6) is set up (we recommend to use the MultiNest sampler!), please proceed as follows:

1) Clone this repository

`git clone https://github.com/fkoehlin/kids450_cf_likelihood_public.git`

2) Copy `__init__.py` and `kids450_cf_likelihood_public.data` from this repository into a folder named `kids450_cf_likelihood_public` within `/your/path/to/montepython_public/montepython/likelihoods/`.

(you can rename the folder to whatever you like, but you must use this name then consistently for the whole likelihood which implies to rename the `*.data`-file, including the prefixes of the parameters defined in there, the name of the likelihood in the `__init__.py`-file and also in the `*.param`-file.)
 
3) Set the path to the data folder (i.e. `KiDS-450_COSMIC_SHEAR_DATA_RELEASE` from the tarball available at 'http://kids.strw.leidenuniv.nl/sciencedata.php') in `kids450_qe_likelihood_public.data` and modify parameters as you please (note that everything is set up to work with `kids450_cf.params`).

4) Copy the folder `CUT_VALUES` from this repository also into the data folder (`KiDS-450_COSMIC_SHEAR_DATA_RELEASE`).  

5) Start your runs using e.g. the `kids450_cf.params` supplied in the subfolder `INPUT` within this repository.

6) Contribute your developments/bugfixes to this likelihood (please use a dedicated branch per fix/feature).

7) If you publish your results based on using this likelihood, please consider citing [Köhlinger et al. 2019 (arXiv:1809.01406)](http://adsabs.harvard.edu/abs/2018arXiv180901406K) and please cite [Hildebrandt et al. 2017 (MNRAS, 465, 1454)](http://adsabs.harvard.edu/abs/2017MNRAS.465.1454H) for the KiDS-450 data and also all relevant references for MontePython and CLASS.

Refer to `run_with_multinest.sh` within the subfolder `INPUT` for all MultiNest-related settings that were used for the fiducial runs.

WARNING: This likelihood only produces valid results for `\Omega_k = 0`, i.e. flat cosmologies!

For questions/comments please use the issue-tracking system!
