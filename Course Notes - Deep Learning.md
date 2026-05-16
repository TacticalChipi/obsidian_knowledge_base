1. Notation Used
Notation used borrows heavily from *The Elements of Statistical Learning by T. Hastie, R. Tibshirani and J. Friedman* and adapted to more informal ML courses that focus more on implementation than in statistical theory:
- An input variable will be denoted as $X$ and its components by $X_j$.
- Quantitative outputs will be denoted equivalently by $Y$ and qualitative outputs by $G$.
- Observed values are written in lowercase, for instance the *i*th observed value of $X$ is written as $x_i$ where $x_i$ is again a scalar or a vector.
- Matrices are represented by bold uppercase letters; for example a set of N input *p*-vectors $x_{i}, i=1,...,N$  would be represented by the $N$ x $p$ matrix **$X$**.

Relaxed more commonly used notation in ML courses:
- In general, the differentiation between observed variable (lowercase) and generic variable (uppercase) can be dropped to use only lowercase. If this convention is dropped then an upper case would be reserved for matrices without need to be bold and *i* and *j* indexes would denote strictly rows and columns respectively.
- In this case then, a lowercase indexed variable will be always an observed value and an unindexed variable will represent the generic input or output variable.


The general expression for a forward pass in a densely connected traditional neural network would be:
$$z^{[l]} = W^{[l]}a^{[l-1]} + b^{[l]}$$
$$a^{[l]} = \sigma(z^{[l]})$$
With $a^{[0]} = x$ and $l$ being the layer number starting with $l = 0$ for the input later and $\sigma$ being the activation function for layer $l$. This basic neural network architecture is commonly known as a multilayer perceptron (MLP) with the most basic configuration corresponding to a single layer perceptron (1 input, 1 hidden and 1 output layers although typically only hidden layers are counted in the architecture description.
