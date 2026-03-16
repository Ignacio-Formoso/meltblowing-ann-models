# ANN Models for Predicting Fiber Attenuation in Melt-Blowing

This repository provides an Excel implementation of artificial neural network (ANN) models developed to predict fiber attenuation in the melt-blowing process.

The models are presented in the article:

Formoso, I.
**Optimizing Melt-Blowing Nozzles for Small-Diameter Fibers: An Artificial Neural Network Framework**.
*Fibers and Polymers*.
https://doi.org/10.1007/s12221-025-00919-y

The spreadsheet allows users to evaluate the trained neural networks and estimate fiber attenuation for different combinations of operating conditions and nozzle geometries.

---

## Overview

The melt-blowing process produces micro- and nanofibers by attenuating a molten polymer stream using high-velocity hot air. Predicting the resulting fiber diameter requires capturing the complex interaction between operating conditions and nozzle geometry.

To address this challenge, multilayer perceptron (MLP) neural networks were trained using dimensionless parameters that describe the governing physical mechanisms of the process.

This repository provides a transparent implementation of the trained ANN models, including:

* input normalization parameters
* network weights and biases
* activation functions
* forward propagation calculations

This enables the models to be reproduced or implemented in other computational environments.

---

## Repository contents

The Excel spreadsheet contains two trained ANN models:

**Net_1 — HMA model**

Predicts fiber attenuation in hot-melt adhesive (HMA) melt-blowing systems.

Architecture:

4 → 1 → 1 → 1
Activation functions: tansig → tansig → purelin

**Net_2 — PP model**

Predicts fiber attenuation in polypropylene (PP) melt-blowing systems.

Architecture:

4 → 2 → 1
Activation functions: tansig → purelin

Both models predict the **fiber drawing ratio**:

d′ = d_f / L_Rf

which represents the ratio between the final fiber diameter and the polymer exit diameter.

---

## Input variables

The ANN models use four dimensionless parameters:

**m′ — Air–polymer flux ratio**

m′ = ṁa / ṁf

**T′ — Temperature ratio**

T′ = (Tf + Ta) / (2 Tamb)

**g₁ — Dimensionless air impact point**

g₁ = tan(ψ) L_Rf / D

**g₂ — Polymer-to-air area ratio**

g₂ = (L_Rf / L_R)² (1 / N_a/f)

These parameters capture the combined effects of operating conditions and nozzle geometry on fiber attenuation.

---

## Using the spreadsheet

1. Open the Excel file.

2. Select the desired model:

* **Net_1** for HMA systems
* **Net_2** for PP systems

3. Enter the input variables in the yellow cells using physical values.

4. The spreadsheet automatically performs:

* normalization of inputs to [-1,1]
* ANN forward propagation
* output denormalization

5. The predicted **fiber drawing ratio** is displayed in the results section.

---

## Spreadsheet structure

The Excel file contains the following sheets:

**Nomenclature**
Definition of all variables and symbols.

**Activation_functions**
Transfer functions used by the neural network.

**Net_weights_biases**
Trained ANN weights and neuron biases.

**Net_1**
Implementation of the HMA ANN model.

**Net_2**
Implementation of the PP ANN model.

---

## Reproducibility

The spreadsheet provides a fully transparent implementation of the trained neural networks. All elements required to reproduce the models are explicitly included:

* normalization limits
* neuron weights
* biases
* activation functions
* network architecture

This allows researchers to implement the models in other environments such as MATLAB, Python, or other numerical tools.

---

## Author

Ignacio Formoso

---

## Citation

If you use this model in academic work, please cite the associated article:

Formoso, I.
Optimizing Melt-Blowing Nozzles for Small-Diameter Fibers: An Artificial Neural Network Framework.
*Fibers and Polymers*.
https://doi.org/10.1007/s12221-025-00919-y

---

## License

This repository is released under the MIT License.
