# Causal Discovery in Hawkes Processes by Minimum Description Length
Python Code Package, September 1, 2021

This is the official implementation of **Causal Discovery in Hawkes Processes by Minimum Description Length**.

All our code is in `MDL.ipynb` file in `Code` folder. Methods *ML*, *LS*, *NPHC*, and *ADM4* are implemented in python inside TICK package. 
Information criteria (AIC, BIC, HQ) do not return an output, and this is evident from the code and output provided in the python notebook.
You can find the description of the algorithm MDLH in the paper, along with citations.

## Requirements

The method *NPHC* requires an older version of TensorFlow. You can install it via the following command.

```
!pip install tensorflow==1.15
```
TICK package is also required. It can be installed by
```
!pip install tick
```

## Real Data Experiments

Each synthetic experiment is specified by values dimension *p*, and horizon *T*. For large *p*, one should use sparse graph scenario as the example in the code. 
In the sparse graph scenario,  the degree of a node *deg* is also a variable that should be assigned. 
Number of Monte Carlo MC simulations *N* should be as large as computationally possible. One can change the experimental setting via the following block in the notebook:
```
uni_adj_lb = 0.1  # lowest value for influence matrix alpha
uni_adj_ub = 0.2  # highest value for influence matrix alpha
uni_bas_lb = 0.5 # lowest value for baseline vector mu
uni_bas_ub = 1.0 # highest value for baseline vector mu
bern_param = 0.3 # ratio of non-zero entries in adjacency matrix gamma
decays = 1 # decay parameter
TH = 0.01 # Threshold for deciding non-zero entries
p = 20
T = 500
N = 500
n_sim = 10  # number of simulations with a single parameter in MC simulations
size = 100 # size of test set
deg = 1
metric = F1_score
```
For more details about synthetic experiment setup please also view the appendix.

## Synthetic data experiments

First we clean the data as described in the paper. Next, we identify shocks (events) in each dimension by rolling a window. With the Hawkes data in hand, 
we can experiment different causal discovery methods.

Disclaimer:  The authors do not claim any copyright or license  to  either the comparison methods or from them adopted codes or the used data.




