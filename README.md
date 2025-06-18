# INTERPOLATING-NEURAL-NETWORK
Neural Network architecture for interpolation of a tabulated Equation of State for neutron stars

We present a full architecture to train and evaluate a Feed Forward Neural Network designed to interpolate tabulated Equations of State for Neutron Stars. 

We've focused on the 2D MODEL: HS(DD2) neutron matter (with electrons) from Compose database https://compose.obspm.fr/eos/2
Inputs:
1. n_B [fm-3]: (0.1E-11 0.1E+02)
2. T [MeV]: (0.10000000E+00, 0.15848932E+03)
3. Y_q → Constant (0)

Outputs:
1. Q1 = p/n_B [MeV]: (0.10, 5.20E+13)
2. Q2 = S/n_B [dimensionless]: [7.51E−4, 1.41E+12]

However it could be extended to EoS with wider number of inputs or outputs and/or greater range.
