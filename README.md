# A Reproducible Hybrid Architecture of Fuzzy Logic and XGBoost for Explainable Tabular Classification of Territorial Vulnerability

## Overview

This study presents a reproducible hybrid framework for explainable classification of territorial vulnerability using heterogeneous administrative tabular data. The proposed approach combines a fuzzy semantic aggregation layer with XGBoost in a two-stage architecture designed to balance interpretability and predictive performance. The work addresses a practical decision-support setting in which territorial units must be classified, ranked, and prioritized under uncertainty, incomplete coverage, mixed feature types, and asymmetric error costs. 

## Research Objective

The main objective of the study is to develop an interpretable and reproducible machine learning framework for identifying highly vulnerable territories from multi-source socioeconomic and administrative data. The task is formulated as a binary classification problem in which the model predicts whether a territory belongs to the high-vulnerability group and then produces a priority-oriented ranking for intervention planning. 

## Dataset and Analytical Basis

The analytical dataset was constructed by integrating **11 heterogeneous administrative sources** into a unified matrix of **166 territorial units** described by **76 features**. The sources cover socio-demographic indicators, vulnerability categories, agricultural production, land resources, tariffs, infrastructure, project activity, budget and tax parameters, and pension-related statistics. To preserve full territorial coverage, missing numerical values were imputed by the median and missing categorical values were replaced with a safe “Unknown” category. The target variable was operationalized from the share of the population belonging to the most vulnerable categories **D + E**, using a quantile-based thresholding strategy. 

## Proposed Method

The proposed methodology consists of a sequential analytical pipeline:

1. **Multi-source data integration and entity alignment**
2. **Statistical quality control and preprocessing**
3. **Feature engineering and normalization**
4. **Fuzzy inference for interpretable risk and resilience aggregation**
5. **Data-driven calibration of fuzzy rule weights**
6. **XGBoost-based supervised classification on the expanded feature space**
7. **Threshold optimization for decision-oriented classification**
8. **Final priority ranking of territories**

The hybrid design uses fuzzy logic not as a standalone expert system, but as a feature augmentation layer that produces interpretable aggregate indicators, including fuzzy risk and fuzzy resilience. These fuzzy outputs are then embedded into the machine learning feature space and used by XGBoost to model nonlinear dependencies and higher-order interactions. 

## Mathematical and Computational Logic

The study applies min–max normalization to align heterogeneous indicators, median imputation for robustness to missingness, and triangular membership functions to represent linguistic concepts such as low, medium, and high. Fuzzy rule activations are aggregated into interpretable risk and resilience indices. Their coefficients are calibrated using combined dependence signals derived from **mutual information** and the absolute value of **Spearman correlation**, followed by clipping of negative effects and L1 normalization. The final classifier outputs a probability of high vulnerability, which is converted into a binary decision using an optimized threshold selected to maximize the F1 score under asymmetric practical costs. 

## Experimental Design

The model was evaluated on a **stratified 75/25 split**, corresponding to **124 territories for training** and **42 territories for testing**. The evaluation protocol included hold-out testing, repeated nested cross-validation, bootstrap confidence intervals, ablation experiments, overlap sensitivity analysis for fuzzy membership functions, confusion matrix analysis, SHAP-based interpretation, and permutation importance analysis. This design was intended to evaluate not only predictive quality, but also robustness, interpretability, and decision-support utility. 

## Main Results

The final **Proposed Fuzzy-XGBoost** configuration achieved the best overall practical performance among the compared models on the hold-out test set, with:

* **Test Accuracy = 0.8095**
* **Test Precision = 0.6875**
* **Test Recall = 0.7857**
* **Test F1 = 0.7333**
* **Test ROC-AUC = 0.8291**
* **Integrated Score = 0.768**
* **Working threshold = 0.35**

The confusion-matrix analysis showed that the proposed model reduced the number of missed high-risk territories relative to several competing baselines while maintaining acceptable specificity. This made the model particularly suitable for early detection scenarios where false negatives are more costly than false positives. 

## Comparative Findings

The comparative evaluation included classical baselines, boosting-based tabular models, and ablation variants with and without fuzzy feature augmentation and threshold optimization. The results showed that the proposed framework delivered the most balanced trade-off between vulnerability detection and ranking stability in the tested setting. At the same time, the uncertainty analysis indicated that the performance margins over the strongest baselines were **competitive but modest rather than statistically dominant**, which is an important scientific conclusion of the paper. The contribution of the proposed approach therefore lies not only in predictive performance, but also in interpretability, reproducibility, and threshold-aware decision support. 

## Interpretability and Explainability

Global and local explanation analyses showed that the model relies strongly on demographic and economic features, especially variables related to registered population, investment activity, agricultural output, infrastructure, and employment-related signals. The fuzzy risk component contributed meaningfully to individual predictions, confirming that the fuzzy augmentation layer added explanatory value beyond the raw feature space. The study also included SHAP-based visual analysis and permutation-based feature ranking to make the model behavior transparent and analytically interpretable. 

## Practical Output

A major applied result of the work is the generation of a **priority ranking of territorial units**. Instead of limiting the output to a binary class label, the framework computes a final priority index that combines the predicted probability of high vulnerability with interpretable fuzzy components. This makes the method suitable for practical regional planning, targeted support allocation, administrative prioritization, and scenario-based policy analysis. The final ranked output includes district-level units, KATO identifiers, predicted probabilities, fuzzy risk, fuzzy resilience, and the final integrated priority score. 

## Scientific Novelty

The scientific novelty of the work lies in the following elements:

* development of a **hybrid Fuzzy–XGBoost architecture** for explainable tabular vulnerability classification;
* integration of fuzzy logic as a **reproducible preprocessing and feature engineering layer** rather than as an isolated expert subsystem;
* introduction of a **data-driven fuzzy coefficient calibration mechanism** based on statistical dependence;
* incorporation of **probability-threshold optimization** as an essential component of the analytical workflow;
* transformation of the classification result into a **quantitative territorial priority ranking** for decision support.

These contributions position the framework as a transferable template for explainable machine learning on structured administrative data under uncertainty. 

## Limitations

The paper explicitly acknowledges several limitations:

* the dataset is relatively small (**166 observations**);
* the experiments were conducted within a **single territorial context**;
* the current **fuzzy resilience** component remained inactive under the present rule specification;
* the generalizability of the framework across other regions, time periods, and administrative contexts still requires additional validation.

These limitations do not invalidate the framework, but indicate directions for further methodological refinement and broader empirical verification. 

## Conclusion

The study demonstrates that combining fuzzy semantic aggregation with XGBoost yields a reproducible and interpretable framework for territorial vulnerability classification and ranking. The proposed architecture links semantic transparency, nonlinear predictive modeling, calibrated decision thresholds, and operational prioritization within a single pipeline. The final results confirm that the framework is suitable not only for predictive classification, but also for practical decision support in territorial management and targeted social policy planning. 
