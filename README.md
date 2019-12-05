# ALMA and NACO observations towards J1407

This repository contains the reduced images and scripts for the paper "ALMA and NACO observations towards the young exoring transit system J1407 (V1400 Cen)" by M.A. Kenworthy, P.D. Klaassen, M. Min, M. van de Marel, A.J. Bohn, M. Kama, A. Triaud, J. Monkiewicz, E. Scott, E.E. Mamajek, accepted for publication in Astronomy and Astrophysics on 16 Nov 2019.

Questions on the paper and scripts to Matthew Kenworthy kenworthy@strw.leidenuniv.nl

The `directory paper/` contains the TeX and final figures for the paper. All the figures are generated using scripts in this repository.

`alma_analysis/` contains the reduced ALMA image of the J1407 field and a Jupyter notebook with the astrometric analysis.

`naco_analysis/` contains the data from the NaCo camera on the Very Large Telescope along with the contrast limit plots.

`ring_models/` contains the configuration scripts for the MCMax models of the J1407b ring system, the resultant output files, and the Python notebooks used to generate the plots in the paper.


## Dependencies

`astropy`

`aplpy`



## Licence

All the scripts are released under a BSD 2-Clause "Simplified" License.