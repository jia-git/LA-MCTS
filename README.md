# LA-MCTS
The code is based of paper [Learning Search Space Partition for Black-box Optimization using Monte Carlo Tree Search](https://arxiv.org/abs/2007.00708).

## Component
LA-MCTS has three major components:

### Main Loop
At each iteration, main loop builds the Monte Carlo search tree, selects next node, and samples on selected nodes.

### Classifier
Classifiers define rules to split a node, they also predict if a sample belongs to the node. Currently there are several
builtin classifiers:
#### SVM Based Classifiers
In these classifiers, some cluster algorithm is used to label the samples, then SVM is used to classify the samples.
Builtin cluster algorithms include:
* KMeans
* Threshold
* Linear regression
#### Regression Classifier
A regressor is used to fit samples, then a threshold (median or mean) is used to separate them.

### Samplers
Samplers draw samples in node space. Currently builtin samplers include:
* Random sampler
* Bayesian sampler
* TuRBO sampler
* CMAES sampler
* Nevergrad sampler

Users may provide their own classifier and/or sampler by implementing Classifier and Sampler interface.

## Usage
An example can be found at [example_opt.py](./example/example_opt.py).

## Docs
Detailed docs can found at [here](https://facebookresearch.github.io/LA-MCTS/).

## License
LA-MCTS is under [Apache License 2.0](./LICENSE).
