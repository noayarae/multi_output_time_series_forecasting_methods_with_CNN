## Multi_output_methods_for_long_term_time_series_using_CNN

### Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting using Convolutional Neural Networks
##### **Authors:** Efrain Noa-Yarasca, Javier M. Osorio Leyton, and Jay Angerer

#### Overview
This repository provides datasets and Python implementations of convolutional neural network (CNN) models for long-term aboveground biomass time-series forecasting. It accompanies the study published in Machine Learning and Knowledge Extraction (2024).


## Methodological Background and Development

Multi-step time-series forecasting methods have evolved to address the challenge of predicting multiple future observations while accounting for dependencies among forecasted values.

Early approaches included the **Recursive** and **Direct** strategies. Recursive forecasting uses a single model to predict one time step at a time, feeding previous predictions into subsequent iterations. Direct forecasting instead trains a separate model for each forecasting horizon, avoiding the recursive propagation of prediction errors but treating each horizon independently.

The **Direct-Recursive (DirRec)** method combined these two concepts by using separate models for each forecast step while incorporating previous predictions into subsequent model inputs.

Later, multi-output approaches introduced alternative ways to predict several future observations simultaneously. The **Multiple-Input Multiple-Output (MIMO)** method predicts the entire forecasting horizon using a single model. The **DIRMO** method extends this concept by dividing the forecasting horizon into smaller segments, each predicted simultaneously by a separate model.

Building on these established strategies, Noa-Yarasca et al. (2024) introduced two additional multi-output forecasting methods: **RECMO** and **DirRecMO**. These methods were developed to combine multi-output prediction with recursive and direct-recursive forecasting structures.

- **RECMO (Recursive Multi-Output)** combines the recursive and MIMO strategies. It predicts multiple future observations at each iteration, uses those predictions as inputs for the next iteration, and maintains a constant input-window size through a sliding-window mechanism.

- **DirRecMO (Direct-Recursive Multi-Output)** combines the direct-recursive and MIMO strategies. It also predicts multiple observations at each iteration and incorporates previous predictions into subsequent inputs. However, it uses a distinct model at each iteration and retains the original observed input window, resulting in an expanding-window structure.

These methods introduce two alternative ways of organizing multi-output predictions across a forecasting horizon. Their performance depends on the forecasting horizon, the number of outputs predicted per iteration, and the characteristics of the time series.



#### Methodological contribution
Multi-step time-series forecasting strategies differ in how they generate predictions across multiple future time steps. Established approaches include Recursive, Direct, Direct-Recursive (DirRec), DIRMO, and Multiple-Input Multiple-Output (MIMO).

This study introduces two additional forecasting strategies that extend existing multi-output methods by combining their prediction structures:
- **RECMO** (Recursive Multi-Output): Combines the recursive forecasting strategy with the MIMO approach, integrating recursive prediction with multi-output forecasting.
- **DirRecMO** (Direct-Recursive Multi-Output): Combines the direct-recursive strategy with MIMO, integrating horizon-dependent prediction with multi-output forecasting.

These strategies extend the available methodological options for multi-step forecasting by introducing alternative ways to structure predictions across multiple future time steps.

**Repository contents**

This repository includes the aboveground biomass time-series datasets and Python code for implementing and evaluating CNN-based forecasting models using the established strategies and the two proposed methods, RECMO and DirRecMO.

**Reference**

- Noa-Yarasca, E., Leyton, J. M. O., & Angerer, J. P. (2024). Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting Using Convolutional Neural Networks. Machine Learning and Knowledge Extraction, 6(3), 1633–1652.

https://doi.org/10.3390/make6030079


