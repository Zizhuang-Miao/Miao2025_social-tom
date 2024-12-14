# Scripts for *Common and distinct neural correlates of social interaction perception and theory of mind*

Zizhuang Miao

This repo hosts the codes accompanying the article titled "Common and distinct neural correlates of social interaction perception and theory of mind" ([link here]()). Readers should be able to re-use most of those codes to replicate experiments and analyses.

## Software dependency
The analyses were performed in Python 3.9 and MATLAB R2022b. Besides many commonly used packages (e.g., `pandas` and `numpy` in Python), I used the following open-source packages:
+ [SPM12](https://www.fil.ion.ucl.ac.uk/spm/software/spm12/)
+ Several packages in [CANLab toolbox](https://github.com/canlab)
+ [NLTools](https://nltools.org/)
+ [Nilearn](https://nilearn.github.io/stable/index.html)

Additional packages needed will be mentioned where necessary.

## File navigation
Below is a high-level overview of the naming and functions of the scripts in this repo:

+ `stimuli`: The audios and texts of narratives used in the experiments; each .wav and .txt file was used in one trial. Additionally, `all_narratives` contains the text documents for each of the eight narratives. Note that there are two more audio files than text files, which were used in the practice trials of the online experiment.
+ `exp_online`: The scripts, condition files, additional stimuli, and dependencies (PsychJS) needed to run the online experiment on Pavlovia.org.
+ `exp_fmri`: The scripts and condition file used to run the experiment during fMRI scanning. Note that Psychtoolbox (MATLAB) is needed to run the scripts.
+ `analysis_behavior`: Scripts used to analyze online participants' rating data and experimenters' annotations. 
  + `preprocessing`: Scripts for organizing and cleaning data. They should be run in the sequence of the numbers in file names.
  + `analyzing`: Scripts for calculating metrics for online particpiants' ratings and generating reports. Figure 2 in the paper can be reproduced using those scripts.
+ `analysis_fmri`: Scripts used to analyze and visualize fMRI data
  + `preprocessing`: Preprocessing of fMRI data was done using a Docker image of fmriprep on a computing cluster. Specific parameters for fmriprep can be read from the shell script.
  + `first_level_GLM`: The scripts used to build design matrices and run first-level GLM. Only the script for one GLM (with both social interactions and theory of mind in the model) was provided as an example; other models were run by simple variants of that script.
  + `second_level_GLM`: Scripts in this folder take the beta maps from first-level GLMs as inputs. Several lines of analyses were performed:
    + Group level t-tests. One example t test analysis was provided in `tom_social.mlx`, based on SPM and CANLab toolbox. The results were then visualized on the surface using Nilearn (in `visulization_allinresults.ipynb`). Related to Figures 3a, 4a, 5a, and 5b.
    + Bayes factor analysis. It was done in `bayes_factor.mlx`. Similarly, the results were visualized on the surface. Related to Figure 6.
    + Mask-based analysis (extract beta values within pre-defined brain masks and perform analysis on the group level). Two example analyses were provided in `mask_based_analysis.mlx`. Related to Figures 3b, 4b, 5c, and 6b.
