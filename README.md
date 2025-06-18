# INTERPOLATING-NEURAL-NETWORK
We present a full architecture to train and evaluate a Feed Forward Neural Network designed to interpolate tabulated Equations of State for Neutron Stars. 

We've focused on the 2D MODEL: HS(DD2) neutron matter (with electrons) from Compose database https://compose.obspm.fr/eos/2. 
However it could be extended to EoS with wider number of inputs or outputs and/or greater range.

Inputs:
1. n_B [fm-3]: (0.1E-11 0.1E+02)
2. T [MeV]: (0.10000000E+00, 0.15848932E+03)
3. Y_q → Constant (0)

Outputs:
1. Q1 = p/n_B [MeV]: (0.10, 5.20E+13)
2. Q2 = S/n_B [dimensionless]: [7.51E−4, 1.41E+12]


The code contains several ordered modules:

A. preparation_of_data: Upload tabulated data, create indexed map for inputs and ouputs and preprocess data for NN training (splitting into training/validation/data sets, normalization and transforming into torch.nn tensors).

B. neural_network: Definition of the feed forward network with flexible structure allowing dynamic change of hyper-parameters.

C. random_search: Automatized RandomSearchCV with flexible cross validation to find optimal hyper-parameters for our model. 

D. final_models: Retraining of top performing model from RandomSearchCV to further prove generalization and study metrics for generated predictions.

E. global_interpolation: Interpolation scheme designed to study local interpolation on triplets of data based on the globally trained model and comparision with B-Splines performance.

F. local_interpolation: Interpolation scheme designed to study local interpolation on triplets of data with the previous local training on a FFNN on data triplets and comparision with B-Splines performance.
