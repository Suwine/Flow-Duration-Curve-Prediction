# Flow-Duration-Curve-Prediction-
**author**: Tian Lan, Jiajia Zhang

## Datasets: 
"01-data" folder contains research data of 201 MOPEX basins and Hanjiang River Basin(Hanjiang, Mumahe, Xunhe).
## Main analysis codes:
### Regionalization
- `senstivity_analysis.m`:To determine the optimal number of clusters for the K-means algorithm.
- `K_means_test.m`:Run the K-means algorithm with the number of clusters determined by 'sensitivity_analysis.m'.
- `RF.m`:Transfer model parameters from the hydrologically most similar basins to ungauged basins.
### Delayed flow seperation
- `Batch processing of baseflow.R`:Batch process all CSV files in a folder, splitting baseflow according to N:1-90.
- `Batch processing of DFI.R`:Calculate the DFI values for 90 time blocks.
- `MAM_MQ.R`:Calculate the maximum and average flow values.
- `Combination.R`:Merge the outputs from 'Batch processing of DFI.R' and 'MAM_MQ.R' into one table.
- `Batch processing of CDCs.R`:Plot the CDC curve.
### Vine copula structure

#### Vine copula
- `Vine copula CDF.R`:Based on the selected optimal Vine copula structure, calculate the joint CDF for four delayed flows.

#### Evaluation
- `FDC.m`:Plot the FDC curve based on the CDF data obtained from the 01 Vine copula section
- `Heatmap_RMSE.py`:Plot a heatmap based on the RMSE values between the constructed FDC and the actual FDC.
### Bayesian-based parameter estimation
Estimate the parameters of the Copula function, this section of the code is from Sadegh, M., Ragno, E., and AghaKouchak, A. (2017), Multivariate copula analysis toolbox (MvCAT): Describing dependence and underlying uncertainty using a Bayesian framework, Water Resources Research, 53(6), 5166-5183.

## References:
Ghotbi, S., Wang, D. B., Singh, A., Mayo, T., and Sivapalan, M. (2020a). "Climate and landscape controls of regional patterns of flow duration curves across the continental United States: A statistical approach." Water Resources Research, 56(11).
Ghotbi, S., Wang, D. B., Singh, A., Bloschl, G., and Sivapalan, M. (2020b). "A new framework for exploring process controls of flow duration curves." Water Resources Research, 56(1).
Sadegh, M., Ragno, E., and AghaKouchak, A. (2017), Multivariate copula analysis toolbox (MvCAT): Describing dependence and underlying uncertainty using a Bayesian framework, Water Resources Research, 53(6), 5166-5183.
Stoelzle, M., Schuetz, T., Weiler, M., Stahl, K., and Tallaksen, L. M. (2020). "Beyond binary baseflow separation: A delayed-flow index for multiple streamflow contributions." Hydrology and Earth System Sciences, 24(2), 849-867.
