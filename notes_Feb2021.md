# Notes for February 2021

- To run and interactive job with GPU usage in SLURM:
```bash
srun --gres=gpu:1 --pty bash
```
- To look at GPU usage you can use Ganglia or either of these commands from the terminal:
```
nvidia-smi
```
```
module load gpu-stat
gpustat --watch
```
- Notes on `htop` (for Xena): 
    - look at "load average"
    - if ~16 then all 16 cores are being used efficiently
    - if > 16 then you are overloading
    - if < 16 then you are not allocating resources properly

- Compiling and running CUDA code (e.g. timing matrix multiplication):
``` 
module load cuda
nvcc matmat.cu -o matmul
./matmul > output.txt
```

## Docker + Spack

- Singularity is used for HPC systems (like Docker but completely local, ie. no permissions problems)
- Docker terminology:
    - **Image:** A package with all the dependencies and information needed to create a container. An image includes all the dependencies, deployment, and execution configurations to be used by a container. An image is immutable once it has been created.
    - **Container:** An instance of a Docker image. A container represents the execution of a single application, process, or service and consists of the contents of a Docker image, an execution environment, and a standard set of instructions.
- Installing Docker and using with Spack (a tutorial):
    1) Install Docker
    2) `docker pull centos:7` 
        - may need docker login
        - use centos7 because it is what is the basis of all CARC clusters
        - could also emulate an ubuntu system with `docker pull ubuntu`
    3) `docker run -it centos:7`
        - this will load the docker container
    4) `yum group install "development tools"`
        - centos uses `yum`
        - automatically logged in as `root` so no permission problems
        - first need to install a bootstrap compiler
        - "development tools" will install very early version of g++ which can be used later to install later versions
        - it also installs early versions of e.g. python & perl
    5) `yum install git`
    6) `git clone https://github.com/spack/spack ~/spack`
    7) `. ~/spack/share/spack/setup-env.sh`
        - the `.` is shorthand for `source`
    8) `spack list`
        - this will list all available spack packages 
        - not recommended since there are a lot (~5200)!
    9) `spack compilers`
        - this will list available spack compilers
    10) `spack install <package name>`
        - time to start installing packages! e.g. `mpileaks`
    11) In a new terminal: `docker ps`
        - this lists information related to the running Docker processes
    12) `docker commit <container id>  <name>`
        - this will save the container you are working on as an image
    13) `docker run -it <name>`
        - now you can load the image any time you want using the name you gave it when you last saved
