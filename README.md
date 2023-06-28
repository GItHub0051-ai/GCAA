# GCAA
This is a project about Global Context Attention Architecture (GCAA)

# Introduction
GCAA is a framework with global focus， which is made up of three parts. The core component is Context Excavate Module(CEM), which is a Transformer-style encoder block. It is developed to capture long-range sentiment dependencies in consecutive utterances for simulating the continuous expression. Short-rang Features Integration Strategy(SFIS) is designed to enhance the context sensitivity of each micro-feature. Modal Weight Update Strategy(MWUS) is applied for dynamically adjusting the heterogeneous modal weights during modal fusion process.

![CEMwithPLM](/Images/CEMwithPLM.jpg)

# Usage
Here is how to run the code.

## Requirement
* Python 3.8.0+
* Pytorch 1.2.0
* CUDA 11.6
* tqdm 4.65.0
* transformers 4.28.1

## Train
Begin training.
* Dataset: get in the *DATA* file.
* Epoch: 200.
* Learning rate: 1e-5.
* Dropout : 0.1.

#Result & Analysis
## Effectiveness of CEM
<img src="/Images/JS_Divergences.jpg" width="600" height="420"/><br/>
Here we show the JS divergence distribution with and without CEM. As the number of batches increases, the dispersion of JS values using CEM decreases significantly. It shows that CEM can increase the feature correlation between sentences, and further proves that CEM is able to capture the emotional dependence between successive sentences.

## Comparison with recent stat-of-the-art approaches on MOSI dataset
| Model | Acc_2 | F1 | MAE | Corr |  
| MISA | 88.52 | 88.58 | 0.605 | 0.848 |  
| CENet | 89.48 | 88.45 | 0.597 | 0.861 |  
| GCAA | 90.70 | 89.68 | 0.595 | 0.863 |  
Compared with the most advanced approaches, the proposed method achieves the best performance on all four indicators.
