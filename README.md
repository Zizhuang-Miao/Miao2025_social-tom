# Scripts for *Common and distinct neural correlates of social interaction perception and theory of mind*

Zizhuang Miao

This repo hosts the codes accompanying the article titled "Common and distinct neural correlates of social interaction perception and theory of mind" ([link here]()). Readers should be able to re-use most of those codes to replicate experiments and analyses.

## Software dependency
The analyses were performed in Python 3.9 and Matlab R2022b. Besides many commonly used packages (e.g., `pandas` and `numpy` in Python), I used the following open-source packages:
+ Several packages in [CANLab toolbox](https://github.com/canlab)
+ [NLTools](https://nltools.org/)
+ [Nilearn](https://nilearn.github.io/stable/index.html)

Additional packages needed will be mentioned where necessary.

## File navigation
Below is a high-level overview of the naming and functions of the scripts in this repo:

+ `stimuli`: The audios and texts of narratives used in the experiments; each .wav and .txt file was used in one trial. Additionally, `all_narratives` contains the text documents for each of the eight narratives. Note that there are two more audio files than text files; they were used in the practice trials of the online experiment.
+ `exp_online`: The scripts, condition files, additional stimuli, and dependencies (PsychJS) needed to run the online experiment on Pavlovia.org.
+ `exp_fmri`:
+ `analysis_behavior`: Scripts used to analyze online participants' rating data and experimenters' annotations. 
  + `preprocessing`: Scripts for organizing and cleaning data. They should be run in the sequence of the numbers in file names.
  + `analyzing`: Scripts for calculating metrics for online particpiants' ratings and generating reports. Figure 2 can be reproduced here.
+ `analysis_fmri`: 
