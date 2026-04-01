# Distinguishing_SIDM_From_CDM_With_LISA_2

This code is used to determine the number of massive black hole mergers that would need to be observed by LISA to distinguish dark matter that has non-gravitational self interactions from dark matter that does not, due to the delaying effect of self-interacting dark matter on massive black hole mergers. This is a proof-of-concept study that should be followed by future work with a larger simulation suite and more realistic modeling, such as a velocity-dependent cross section.

In this work we use simulations of two Milky Way - mass galaxies to build sets of cosmic times and mass ratios for massive black hole mergers. These are used to construct cumulative distribution functions (CDFs) which are inverted to produce inverse CDFs. These are used in inverse transform sampling to generate sets of cosmic times and mass ratios to simulate what LISA might see. We then use a KS test to compare cosmic times and mass ratios for the two dark matter models, varying the number of mergers observed over the course of the LISA mission. This allows us to determine the number of mergers LISA would need to observe over its lifetime to distinguish between dark matter that has self-interactions (SIDM) and dark matter that does not (CDM), when comparing either cosmic times or mass ratios of mergers. In this work, we wish for the 95th percentile for the p-value (out of a set of 10,000 p-values) to be below the significance threshold, 0.05. This ensures that the p-value is below the significance threshold at least 95 percent of the time. 

Note that the relevant data (the cosmic times and mass ratios of mergers in the simulations) is included in the notebooks.

Directions for Using Each File:
For all files: 
The notebooks load certain fonts near the top of the code, which are used in the plots. If you wish to use the exact fonts we used, you would need to ensure that these are installed, and adjust the directory personal_path = "/home/hoelsczj/Library/static/" to point to the correct place for this font file. Alternatively, one can simply delete this portion and use the default font for matplotlib. 

1. Cosmic_Time_Pipeline.ipynb:
Near the top of the file we have: Number_Mergers_Seen_LISA=70
This number can be adjusted to vary the number of mergers LISA sees over the course of the mission. This is the only input the user needs to change, beyond adjusting file paths for saving plots, so that they save to their desired directories. Near the bottom of the notebook, it prints the average p-value and the 95th percentile. These are the quantities that are of interest, in addition to the wedge plot, which is also displayed near the bottom of the notebook. 

2. Mass_Ratio_Pipeline.ipynb:
The directions for using this are identical to the directions for Cosmic_Time_Pipeline.ipynb.

3. Average_P_Value_95th_Percentile.ipynb:
This notebook plots the average p-value, the 95th percentile for the p-value, and the significance threshold against the number of mergers seen by LISA over the course of the mission. This encodes the number of mergers seen in “x”, the average p-values in “pvalues” and the 95th percentile values in Percentile95. This would need to be adjusted for both cosmic time and mass ratio to match the values from the user’s runs. The user should also adjust the pathways in the notebook so that plots save to their desired directories. 

4. L3_Noise.txt:
This encodes the noise curve for LISA. The user needs to download this file, though the user does not need to edit it in any way. 

5. SNR_Ranges.ipynb:
This notebook computes SNR ranges for the mergers in GM7 by sampling inclination and spin from distributions. The user does not need to change anything here, beyond adjusting paths to their desired directories for L3_Noise.txt, for saving plots, or for loading fonts used in plots. 
