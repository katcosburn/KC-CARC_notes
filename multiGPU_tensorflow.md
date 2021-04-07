# Using TensorFlow on Multiple GPUs #

TensorFlow is a popular open source platform for machine learning that enables parallelism across GPU cores. This parallelism ends up amounting to considerably 
reduced computation times, as performance is scaled with data size, unlike CPU-based operations, which do not scale with the data at a constant rate (for an
in-depth look, check out the [Introduction to Tensorflow Quickbyte](https://github.com/UNM-CARC/QuickBytes/blob/master/Tensorflow_documentation.md)).

## Overview of Conda Environments ##

In order to get started, you must first install the GPU-enabled version of TensorFlow. Instructions for setting up and doing that within a conda environment can be
found in this Quickbyte:

https://github.com/UNM-CARC/QuickBytes/blob/master/Install%20deep%20learning%20packages.md

Note that in addition to the GPU-enabled version of TensorFlow, you will also want to follow step 6 and install `numpy, pandas, matpotlib, scikit-learn`. It is
also recommended that you use `conda install ipykernel` so that you can run your code on CARC's JupyterHub interface (which is helpful for plotting).

## Multiple-GPU Processes ##

On Xena, there are 4 dualGPU nodes available and this tutorial will cover the use of one node with 2 GPUs to run a neural network code. The documentation for how to
do this, in generl, can be found [here](https://keras.io/guides/distributed_training/).
