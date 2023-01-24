# CoIR Code

All scripts and code to run the CoIR<sub>LS</sub> algorithm can be access on GitHub
[CoIR](https://github.com/lburleigh/lb_dissertation)


## Directory Setup

Store functional nifti fMRI files in the following directory: data > raw > pymvpa > <subject#> > <fmri_files>.nii.gz

ROI binary group masks should be stored in the directory: data > raw > roi > <mask_name>.nii.gz


## Script 1

Script 01_apply_roi.py should be run first. This script takes in the functional fMRI nifti files and a binary ROI mask in order to create a final .npz which stores the relevant task, mask, and fMRI information to be used in the following algorithm.

First, edit the variables assigned in lines 13-18 of the 01_apply_roi.py script. 

- Line 13 denotes that the condition tuple contains a phase, experiment, mask, and subject. 
- Line 16 defines the phases. In the study this code was designed for, the two phases are two sets of tasks that were performed by each participant.
- Line 17 defines the experiments. In the study the code was designed for, the experiments are the two task types given in each phase. The "hab" experiment refers to a habituation task in which the instructions were learned and performed while the "task" experiment refers to the main task in which fear conditioning was introduced. 
- Line 18 defines the mask name **wihtout** .nii.gz
- Lines 13 and 19-23 may need to be edited if any of the previous variables are not relevant to your study. 

When all variables are adjusted to the study data, run this python script.


## Script 2

Script 02_fit_models.py takes in the .npz file created from 02_fit_models.py to run the CoIR<sub>LS</sub>.

First, edit the variables assigned in lines 7-19 of the 02_fit_models.py script. 

- Line 7 specifies the phase to run the algorithm on
- Line 8 defines the task to run the algorithm on
- Line 9 defines the ROI to run the algorithm on, again leaving out .nii.gz of the filename
- Line 10 defines the classification trials of interest. In the study this code was created for, the goal was to classify whether each trial was a "csp" or "csm"
- Line 15 defines the alpha hyperparameter. Multiple alpha values can be provided in a list for this variable to perform a hyperparameter search, identifying the ideal value 
- Line 17 defines the lambda hyperparameter. Multiple lambda values can be provided in a list for this variable to perform a hyperparameter search, identifying the ideal value 
- Line 19 defines the variables that are included in the filename of the .npz. If no variables were removed from the previous script (01_apply_roi.py), no variables will need to be removed or changed from this line.

When all variables are defined appropriately for the study data at hand, run the 02_fit_models.py script.