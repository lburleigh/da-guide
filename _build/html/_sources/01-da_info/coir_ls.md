# CoIR<sub>LS</sub>

The CoIR<sub>LS</sub> framework is completed in 4 steps: 
1. encode domain covariates with one-hot encoding
2. construct the identity matrix, centering matrix, probability matrix, and a matrix denoting unlabeled target data as 0s
3. construct kernel matrix and linear kernel
4. compute and return the classifier based feature mapping. 

## Input
Inputs required include: 
- data matrix of source and target data
- vector of training labels
- domain covariates

## Hyper-Parameters
Hyper-parameters (i.e., values that control the model’s learning process) include: 
- lambda  ($\lambda$), which controls the importance of dependence on domain covariates
- alpha ($\alpha$)

Optimal hyper-parameters can be found using leave-one-domain-out cross validation on source domain data. 

The algorithm is not sensitive to the trade-off parameter, indicating the covariate-independence regularization importance stability (see Fig. 3a).

![Hyperparameters](images/CoIRsenslamb.JPG)

<b>Fig. 3 - Sensitivity of classification accuracy with respect to hyper-parameters of CoIRLS on five multi-source brain decoding tasks from OpenNeuro </b>