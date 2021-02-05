# Notes for February 2021

- To look at GPU usage you can use Ganglia or either of these commands from the terminal:
```
nvidia-smi
```
```
module load gpu-stat
gpustat --watch
```
- Notes on `htop` (on Xena): look at "load average", if ~16 then all 16 cores are being used efficiently, if higher then you are overloading, if lower then you are not allocating resources properly

- Compiling and running CUDA code:
``` 
module load cuda
nvcc <filename>.cu -o <executable>
./<executable> > output.txt
```

## Docker + Spack