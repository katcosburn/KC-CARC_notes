# Installing GPU-Enabled Tensorflow and Pytorch on Xena

This tutorial goes over how to do tensorflow:

(Need to add how to create tensorflow_env)

```bash
module load miniconda3
```
```bash
source activate tensorflow_env
```
```bash
srun --gres=gpu:1 --pty bash
```

This tutorial goes over how to do pytorch:

```bash
module load miniconda3
```
```bash
conda create -n pytorch_gpu python=3.7
```
```bash
source activate pytorch_gpu
```
```bash
conda install pytorch-1.5.0-py3.7_cuda10.1.243_cudnn7.6.3_0.tar.bz2
```
```bash
conda install cudatoolkit=10.1.243
```
