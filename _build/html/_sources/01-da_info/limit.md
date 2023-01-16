# Domain Adaptation Limitation

The use of domain adaptation has an important limitation to be aware of. Unlike other fMRI analyses, domain adaptation must retain a spatial link of voxels across subjects. 

Typically, fMRI data is analyzed across a subset of spatially relevant voxels (i.e., whole brain or a region of interest) after subject scans are similarly oriented to a standardized space, commonly MNI as used in the study below, which allows every subject’s brain to be defined within the same boundaries from a set origin. While activity may commonly occur in concentrated brain space, subject brains are not a 1:1 link of voxel activation, meaning that while fear may activate the insula of both subjects, insula voxel A of subject 001 may not activate identically to insula voxel A of subject 002. Voxel activity is typically assessed across a subset of spatially relevant voxels because brains are similar but not identical. 

Domain adaptation is unable to follow this rationale as voxels are individually weighted based on their contribution to the classification and identifies voxels that correlate with a label across all participants and therefore some voxels will be regressed out during training. The need for voxels to be 1:1 linked across subjects may impact the results as if a feature is unique to the target domain, it will be difficult to identify it as the source domain considers one dimension while the target domain considers both dimensions. 

While this limitation should be thoughtfully considered, domain adaptation remains a considerable step forward in fMRI analysis and the conclusions that can be drawn from the data. Additionally, if voxel to voxel correspondence is given up in domain adaptation, localization of function is also abandoned as the voxel space is.