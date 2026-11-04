## Multi_output_methods_for_long_term_time_series_using_CNN

### Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting using Convolutional Neural Networks
##### **Authors:** Efrain Noa-Yarasca, Javier M. Osorio Leyton, and Jay Angerer

#### Overview
This repository provides datasets and Python implementations of convolutional neural network (CNN) models for long-term aboveground biomass time-series forecasting. It accompanies the study published in Machine Learning and Knowledge Extraction (2024).

#### Methodological contribution
Multi-step time-series forecasting strategies differ in how they generate predictions across multiple future time steps. Established approaches include Recursive, Direct, Direct-Recursive (DirRec), DIRMO, and Multiple-Input Multiple-Output (MIMO).

This study introduces two additional forecasting strategies that extend existing multi-output methods by combining their prediction structures:
- **RECMO** (Recursive Multi-Output): Combines the recursive forecasting strategy with the MIMO approach, integrating recursive prediction with multi-output forecasting.
- **DirRecMO** (Direct-Recursive Multi-Output): Combines the direct-recursive strategy with MIMO, integrating horizon-dependent prediction with multi-output forecasting.

These strategies extend the available methodological options for multi-step forecasting by introducing alternative ways to structure predictions across multiple future time steps.

**Repository contents**
This repository includes the aboveground biomass time-series datasets and Python code for implementing and evaluating CNN-based forecasting models using the established strategies and the two proposed methods, RECMO and DirRecMO.

**Reference**
Noa-Yarasca, E., Leyton, J. M. O., & Angerer, J. P. (2024). Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting Using Convolutional Neural Networks. Machine Learning and Knowledge Extraction, 6(3), 1633–1652.

https://doi.org/10.3390/make6030079


