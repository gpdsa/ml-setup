# ML Environment Setup

## Anaconda

```bash
# use Python3
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
bash miniconda.sh -b -p $HOME/usr/miniconda
[edit ~/.bashrc]
export PATH=$HOME/usr/miniconda/bin:$PATH

# use SJTU conda mirror
conda config --remove-key channels
conda config --add channels https://mirror.sjtu.edu.cn/anaconda/pkgs/free
conda config --add channels https://mirror.sjtu.edu.cn/anaconda/pkgs/main
conda config --add channels https://mirror.sjtu.edu.cn/anaconda/pkgs/mro
conda config --add channels https://mirror.sjtu.edu.cn/anaconda/pkgs/msys2
conda config --add channels https://mirror.sjtu.edu.cn/anaconda/cloud/pytorch/
conda config --add channels https://mirror.sjtu.edu.cn/anaconda/cloud/conda-forge/ 
# show the channel urls
conda config --set show_channel_urls yes

# configure git push line ending
git config --global core.autocrlf input # 

# create a virtual environment
conda create -n cf python=3.8
conda activate cf
# # remove a virtual environment
# conda env remove -n cf
```

## CUDA v11.7

[CUDA](https://developer.nvidia.com/cuda-11-7-0-download-archive/)

```bash
wget https://developer.download.nvidia.com/compute/cuda/11.7.0/local_installers/cuda_11.7.0_515.43.04_linux.run
sudo sh cuda_11.7.0_515.43.04_linux.run
```

## Python Packages

[PyTorch](https://pytorch.org/).

```bash
pip3 install torch==2.0.0 torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117 # pytorch
conda install numba matplotlib xlutils xlrd xlwt
```
