# Installing GPU-Enabled TensorFlow and PyTorch Environment on Xena

This tutorial will go over how to create and environment on xena that includes everything you need to run GPU-enabled versions of both TensorFlow and PyTorch.

1. Load miniconda (N.B. this is preferable to loading the full anaconda, since it pulls packages directly from internet instead of from the CARC system, ie. you will always get the most up-to-date versions of things):
```bash
module load miniconda3
```
2. Now create a new environment with python version 3.7:
```bash
conda create -n tfpt_combo_env python=3.7
```
3. Load this environment (N.B. on your local machine, instead of `source` use `conda`):
```bash
source activate tfpt_combo_env
```
4. First let's install GPU-enabled PyTorch. For this we need to be in the directory containing the following tarball:
```bash
conda install pytorch-1.5.0-py3.7_cuda10.1.243_cudnn7.6.3_0.tar.bz2
```
5. We also need to install the right CUDA-toolkit version:
```bash
conda install cudatoolkit=10.1.243
```
6. Now let's install GPU-enabled TensorFlow + Keras
```bash
conda install tensorflow-gpu
```
```bash
conda install keras-gpu
```
7. Also might want to install a few other useful things:
```bash
conda install numpy pandas matplotlib scikit-learn ipykernel mpi4py
```
