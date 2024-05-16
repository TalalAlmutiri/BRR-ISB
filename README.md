# BRR-ISB
Bayesian Ridge Regression (BRR)-Iterative Similarity Bagging (ISB) is a new method for multi-omics integration. BRR-ISB has integrated three omics: gene expression, single-nucleotide mutation, and copy number variation. The integrated multi-omics was combined with the drug's chemical structure and used as input to predict drug response.

# BRR
BRR was employed as a strategy for selecting features. This approach involves calculating coefficients to estimate the relevance score of each feature. Bayesian regression focuses on utilizing the Bayesian approach, wherein the estimation of linear models is conducted by considering probability distributions rather than singular point values. The training inputs and outputs influence the posterior probability of the model parameters. Moreover, the Ridge method was embedded with Bayesian regression to reduce the issues of model complexity and multicollinearity by coefficient shrinkage. Most omics data is typically characterized as small-scale, making Bayesian analysis appropriate for such scenarios. The process combines the existing information about the parameter, known as the prior parameter distribution, with the observed data 

![New BRR](https://github.com/TalalAlmutiri/CTGAN_Synthetic/assets/62042702/a1dff350-9995-4bf7-a7e5-d93bfa41c4b3)

# ISB
A new method called Iterative Similarity Bagging (ISB) was introduced as the next step to solve the dimensionality or many features selected from the BRR step. ISB is an unsupervised method that eliminates similar genes according to their distance. One of the neighboring points is considered redundant; therefore, one will be removed. ISB was inspired by the bagging ensemble technique, in which ISB employed columns-based grouping to set features in bags without replacement. Then, the similarity is computed based on Euclidean distance for each group's features or genes. The nearest features inside each bag are considered redundant and removed according to a dynamic threshold.

![ISB Last](https://github.com/TalalAlmutiri/CTGAN_Synthetic/assets/62042702/2d5ed01c-eeed-4e00-9b9f-3e1b509c845c)

# GCN and 1D-CNN
A binary graph was constructed for each input SMILES string, including nodes that include attributes. The features of drugs were learned using Graph Convolutional Networks (GCN). After applying the graph neural network, a fully connected layer (FC layer) was utilized to transform the output into a 128-dimensional representation. The Genomic data was processed using 1D convolutional neural network (CNN) layers to extract the genomic features. Furthermore, 1D pooling was employed to diminish the dimensions of input data. Subsequently, the output was transformed into a 128-dimensional vector representing the cell line. Ultimately, the 256-dimensional vector, a fusion of the drug and the cell line's features underwent two fully connected layers with 512 and 128 nodes before making predictions about the drug response.

![GNN_Model](https://github.com/TalalAlmutiri/CTGAN_Synthetic/assets/62042702/359fc0bb-16ff-467b-b1ad-653d067171d4)

