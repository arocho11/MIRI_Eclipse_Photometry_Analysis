# MIRI_Eclipse_Photometry_Analysis
 Code to reduce and fit MIRI eclipse photometry data for LHS 1140c. 

 Three eclipses were measured on Nov. 27th, July 7th and July 19th. 

 The framework is simple:

- The instrumental systematic signal is fit simulatenously with the astrophysical signal. The notebooks in ModelComparison are used to do this. Each eclipse is fit separately. 

- The astrophysical signal is fit using BATMAN secondary transit. The stellar and planetary parameters need to be changed for a different planetary system. The expected time of transit needs to be adjusted for each observation.

- The instrumental signal can be fitted with an array of models and a second-degree polynomial model. The models are models exponential, linear, 2nd-degree polynomial. The combinations that can therefore be made are: 'exp', 'exp+linear', 'exp+polynomial', 'linear+polynomial', 'polynomial', 'double_exp', 'exp_2nd_order_centroid', 'exp+polynomial_2nd_order_centroid', 'exp+linear_2nd_order_centroid', 'polynomial_2nd_order_centroid', 'linear+polynomial_2nd_order_centroid', 'double_exp_2nd_order_centroid'. 

- The joint fit notebook under ModelComparison can be used to constrain a single eclipse depth and time of mid-eclipse with the three eclipses. Each eclipse has its own coefficient for the exponential model, thes best fit model selected by model comparison. A first-degree centroid model should be added as second-order polynomial centroid model has too many parameters (multipled by number of eclipses) for the MCMC to converge. 