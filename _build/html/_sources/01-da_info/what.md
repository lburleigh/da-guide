# What to Domain Adaptation

Traditional domain adaptation considers each dataset to be a different domain. This is beneficial and widely used in computer vision and natural language processing, however brain activity presents a particular challenge as participants can elicit different patterns of activity for the same cognitive process. 

## CoIR
In order to account for this, the current guide uses the Covariate Independence Regularization (CoIR) framework in which each subject is considered a unique learning task and extracts subject-specific features. Treating each dataset as a different domain as well as each subject as a different domain allows for a more robust model with each unique experiment-subject combination as a unique domain. 