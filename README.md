## Multi_output_methods_for_long_term_time_series_using_CNN

### Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting using Convolutional Neural Networks
##### **Authors:** Efrain Noa-Yarasca, Javier M. Osorio Leyton, and Jay Angerer

#### Overview
This repository provides datasets and Python implementations of convolutional neural network (CNN) models for long-term aboveground biomass time-series forecasting. It accompanies the study published in Machine Learning and Knowledge Extraction (2024).


### Methodological Background and Development

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





### Original Development and Publication

RECMO and DirRecMO were introduced by Efrain Noa-Yarasca, Javier M. Osorio Leyton, and Jay P. Angerer in the following peer-reviewed publication:

Noa-Yarasca, E., Leyton, J. M. O., & Angerer, J. P. (2024). Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting Using Convolutional Neural Networks. *Machine Learning and Knowledge Extraction*, 6(3), 1633–1652.

https://doi.org/10.3390/make6030079

This repository provides the datasets and Python implementations associated with the published study, including the original implementations of RECMO and DirRecMO.






# Extending Multi-Output Methods for Long-Term Aboveground Biomass Time-Series Forecasting Using Convolutional Neural Networks

**Authors:** Efrain Noa-Yarasca, Javier M. Osorio Leyton, and Jay P. Angerer

## Overview

This repository provides datasets and Python implementations of convolutional neural network (CNN) models for long-term aboveground biomass time-series forecasting. It accompanies the peer-reviewed study published in *Machine Learning and Knowledge Extraction* (2024).

The main methodological contribution of the study is the development of two forecasting strategies: **RECMO (Recursive Multi-Output)** and **DirRecMO (Direct-Recursive Multi-Output)**. These strategies extend existing multi-output forecasting approaches by combining their prediction structures with recursive and direct-recursive forecasting mechanisms.

The repository includes implementations of established forecasting strategies alongside RECMO and DirRecMO, allowing their performance to be evaluated and compared under different forecasting horizons.

## Methodological Background and Development

Multi-step time-series forecasting methods differ in how they generate predictions across multiple future time steps and incorporate dependencies among predicted observations.

Several established strategies have been developed to address this problem:

- **Recursive:** Uses a single model to predict one time step at a time. Previous predictions are fed back into the model to generate subsequent predictions.
- **Direct:** Trains a separate model for each forecasting horizon, with each model predicting a specific future time step.
- **Direct-Recursive (DirRec):** Combines recursive and direct forecasting by using separate models for successive forecasting steps while incorporating previous predictions into subsequent model inputs.
- **DIRMO:** Divides the forecasting horizon into multiple groups and uses separate models to predict each group simultaneously.
- **Multiple-Input Multiple-Output (MIMO):** Uses a single model to predict the entire forecasting horizon simultaneously.

Building on these established approaches, Noa-Yarasca et al. (2024) introduced two additional strategies: **RECMO** and **DirRecMO**. Both extend multi-output forecasting by combining the MIMO prediction structure with recursive and direct-recursive mechanisms, respectively.

## Forecasting Strategies

The following figure, reproduced from the published article (Figure 3), illustrates the conceptual structures of the seven forecasting strategies evaluated in the study, including the two proposed methods.

<!-- Upload Figure 3 to the repository and replace the filename below with its actual path. -->

![Comparison of forecasting strategies, including RECMO and DirRecMO](figures/figure3.png)

*Figure 3. Conceptual representation of the forecasting strategies evaluated in Noa-Yarasca et al. (2024).*

## Proposed Forecasting Strategies

### 1. RECMO (Recursive Multi-Output)

RECMO combines the recursive forecasting strategy with the MIMO approach. Instead of predicting a single future observation at each iteration, RECMO predicts multiple future observations simultaneously.

The predicted observations are then incorporated into the input sequence for the next iteration. The oldest observations are progressively removed using a sliding-window mechanism, maintaining a constant input-window size throughout the forecasting process.

A single forecasting model is reused across all iterations.

This approach combines the recursive updating of input sequences with the simultaneous prediction of multiple future observations.

### 2. DirRecMO (Direct-Recursive Multi-Output)

DirRecMO combines the direct-recursive forecasting strategy with the MIMO approach. Similar to RECMO, it predicts multiple future observations simultaneously at each iteration.

However, DirRecMO differs in how it constructs subsequent input sequences. Instead of removing the oldest observations, it retains the original observed input window and adds the predictions generated during previous iterations. Consequently, the input sequence expands as forecasting progresses.

Unlike RECMO, DirRecMO uses a separate forecasting model for each iteration.

This approach combines the multi-output prediction structure with the horizon-dependent model development and recursive incorporation of previous predictions.

## Mathematical Formulation

Let:

- \(y_t\) denote the observed value at time \(t\).
- \(\hat{y}_{t+j}\) denote the predicted value \(j\) time steps ahead.
- \(w\) denote the initial input-window size.
- \(H\) denote the total forecasting horizon.
- \(k\) denote the number of future observations predicted simultaneously at each iteration.
- \(m=H/k\) denote the number of forecasting iterations, assuming that \(H\) is divisible by \(k\).
- \(s\) denote the forecasting iteration, where \(s=1,\ldots,m\).
- \(r=k(s-1)+1\) denote the first forecasting step of iteration \(s\).

The notation \(\hat{\mathbf{y}}_{t+r:t+ks}\) represents the block of \(k\) future observations predicted at iteration \(s\).

### RECMO

In RECMO, the same forecasting function \(f_1\) is used at every iteration. The model predicts a block of \(k\) future observations, which are subsequently incorporated into the input sequence. The input-window size remains constant because the oldest observations are progressively removed.

The general formulation is:

\[
\hat{\mathbf{y}}_{t+r:t+ks}
=
f_1\left(
\hat{y}_{t+r-1},\ldots,\hat{y}_{t+1},
y_t,\ldots,y_{t-(w-r)}
\right)
\]

At the first iteration, the input consists entirely of observed values. At subsequent iterations, previously generated predictions are incorporated into the input sequence, replacing the oldest observations.

### DirRecMO

DirRecMO uses a different forecasting function \(f_s\) at each iteration. The original observed input window is retained, and predictions from previous iterations are added to the input sequence. Therefore, the input sequence expands as the forecasting horizon progresses.

The general formulation is:

\[
\hat{\mathbf{y}}_{t+r:t+ks}
=
f_s\left(
\hat{y}_{t+r-1},\ldots,\hat{y}_{t+1},
y_t,\ldots,y_{t-w+1}
\right)
\]

Each forecasting function is trained for its corresponding iteration. The number of models is \(m=H/k\).

### Relationship with Existing Forecasting Strategies

The parameter \(k\), representing the number of observations predicted simultaneously, determines the relationship between the proposed strategies and established forecasting approaches.

| Strategy | \(k=1\) | \(k=H\) |
|---|---|---|
| RECMO | Recursive | MIMO |
| DirRecMO | DirRec | MIMO |

Thus, RECMO and DirRecMO provide intermediate forecasting structures between single-step and full-horizon multi-output prediction.

## Illustrative Example

Consider a forecasting problem with an initial input window of \(w=24\) observations and a total forecasting horizon of \(H=24\) observations. If \(k=8\), both methods require three iterations to generate the complete forecast.

The input structures differ as follows:

| Iteration | RECMO | DirRecMO |
|---|---|---|
| 1 | 24 observed values | 24 observed values |
| 2 | 8 predictions + 16 most recent observed values | 8 predictions + original 24 observed values |
| 3 | 16 predictions + 8 most recent observed values | 16 predictions + original 24 observed values |

RECMO maintains a constant input-window size and reuses the same forecasting model. DirRecMO retains the original observations, progressively expands its input sequence, and uses a different model at each iteration.

## Experimental Evaluation and Main Findings

RECMO and DirRecMO were evaluated using convolutional neural networks for aboveground biomass time-series forecasting across six Kenyan grassland datasets.

The experimental framework considered multiple forecasting horizons and compared the proposed methods with established strategies, including Recursive, Direct, DirRec, DIRMO, and MIMO.

Forecasting performance was evaluated using the root mean square error (RMSE), while variability across model replications was assessed using the coefficient of variation.

The results demonstrated that RECMO outperformed the established multi-output methods MIMO and DIRMO in the evaluated experiments. DirRecMO showed more moderate performance relative to the established approaches. The findings also highlighted the influence of the number of observations predicted simultaneously (\(k\)) on forecasting performance across different prediction horizons.

These experiments provide an empirical assessment of the proposed strategies and demonstrate their applicability to long-term environmental time-series forecasting.

## Repository Contents

This repository includes:

- Aboveground biomass time-series datasets used in the study.
- Python implementations of CNN-based forecasting models.
- Implementations of established forecasting strategies.
- Implementations of the proposed RECMO and DirRecMO strategies.
- Scripts and materials supporting the experiments reported in the publication.

Refer to the repository files and scripts for implementation details and experimental configurations.

## Publication

The RECMO and DirRecMO forecasting strategies were introduced in the following peer-reviewed publication:

Noa-Yarasca, E., Leyton, J. M. O., & Angerer, J. P. (2024). Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting Using Convolutional Neural Networks. *Machine Learning and Knowledge Extraction*, 6(3), 1633–1652.

https://doi.org/10.3390/make6030079

## Citation

If you use the datasets or implementations in this repository, please cite the original publication:

```bibtex
@article{noayarasca2024extending,
  title={Extending Multi-Output Methods for Long-Term Aboveground Biomass Time Series Forecasting Using Convolutional Neural Networks},
  author={Noa-Yarasca, Efrain and Leyton, Javier M. Osorio and Angerer, Jay P.},
  journal={Machine Learning and Knowledge Extraction},
  volume={6},
  number={3},
  pages={1633--1652},
  year={2024},
  doi={10.3390/make6030079}
}
```



















