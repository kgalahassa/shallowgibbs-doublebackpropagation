
# shallowgibbs-doublebackpropagation
Double Backpropagation Algorithm -- Implementation with the Shallow Gibbs Model

# Double Backpropagation with the Shallow Gibbs Model


## Installation
Install using pip
```pip install shallowgibbs-doublebackpropagation```

## Requirements
* Python 3.6 or greater
* scipy
* tensorflow
* pandas
* numpy
* joblib
* scikit-learn

## Usage
Import the Shallow Gibbs Double Backpropagation module
```import shallowgibbs.doublebackpropagation as SGDBS```
You need to load some initial predictions from the Shallow Gibbs Model, or any alike-Structured Model.
The model requires as parameters: the weigths matrix (W), the biases (b), and the response covariance matrix (Sigma).
The model framework backpropagation is updated per observation using: 



![formula](https://render.githubusercontent.com/render/math?math=MSE\left(y_{i}-\hat{y}_{i}\right)=\left\|y_{i}-\hat{y}_{e s t, i}\right\|^{2})


                                                    
![equation](http://www.sciweavers.org/tex2img.php?eq=MSE%5Cleft%28y_%7Bi%7D-%5Chat%7By%7D_%7Bi%7D%5Cright%29%3D%5Cleft%5C%7Cy_%7Bi%7D-%5Chat%7By%7D_%7Be%20s%20t%2C%20i%7D%5Cright%5C%7C%5E%7B2%7D&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)


 
starting from ```math \hat{\psi}_{0} ``` with the equations:

![equation](http://www.sciweavers.org/tex2img.php?eq=%5Chat%7B%5Cpsi%7D_%7B0%7D&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

```math
\begin{gathered}
\hat{\psi}_{1, i} \longleftarrow \hat{\psi}_{0}-\epsilon_{\psi, 0} \frac{\partial M S E\left(y_{i}-\hat{y}_{e s t, i}\right)}{\partial \psi} \\
\hat{\psi}_{t, i} \longleftarrow \hat{\psi}_{t-1, i}-\epsilon_{\psi, t-1} \frac{\partial M S E\left(y_{i}-\hat{y}_{e s t}, i\right)}{\partial \psi}
\end{gathered}
```

where ```math \psi ``` is the set of parameters (w,b,Sigma) in our case. They are two additional equations that complete those above
explained in reference [2] and well introduced in [1]. There are about the Training data, and test data predictions update. Please read 
reference [2] and the Jupyter Notebook for a guide note of usage and application. 


## Pypi Project Page
 https://pypi.org/project/shallowgibbs-doublebackpropagation/1.0.0/

## Notebook Page
 https://github.com/kgalahassa/shallowgibbs-doublebackpropagation-notebook

## References
[1] Muua, Alejandro, Alahassa, Nonvikan Karl-Augustt. The Shallow Gibbs Network, Double Backpropagation and Differential Machine learning, ScienceOpen Preprints (2021).
 https://www.scienceopen.com/document?vid=9aab283e-130f-4922-accb-20bef8faff9f
 
 
[2] Alejandro Murua, Nonvikan Karl-Augustt Alahassa. Double Back-Propagation and Differential Machine Learning. The Ninth Annual Canadian Statistics Student Conference (CSSC), Jun 2021, Ottawa, Canada. (hal-03265399)
 https://hal.archives-ouvertes.fr/hal-03265399
