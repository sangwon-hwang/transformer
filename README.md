# Cha_Mirae transformer research

## Overview
transformer research w/ Pf. BaekHwan.Cho

## Installation

### all-in-one install
```bash
# conda
conda create -n development -c defaults  -c pytorch -c nvidia -c conda-forge  -c openbabel python==3.7.9 rdkit==2020.03.3.0 openbabel numpy scipy matplotlib pandas scikit-learn jupyter ipython seaborn sphinx pytorch torchvision torchaudio cudatoolkit=11.1
# install torch again..
conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c nvidia
# pip
pip install einops
```

<!-- ### Virtual environment for python 3.7.9

```bash
conda create -n dev -c defaults -c conda-forge  -c openbabel python==3.7.9 rdkit==2020.03.3.0 openbabel numpy scipy matplotlib pandas scikit-learn jupyter ipython seaborn sphinx
``` -->

<!-- #### rdkit installation with conda

```bash
# conda install -y cmake cairo pillow eigen pkg-config
# conda install -y boost-cpp boost py-boost
# conda install -y gxx_linux-64 -->

<!-- conda install -c conda-forge rdkit==2020.03.3.0
```

#### openbabel installation with conda

```bash
conda install -c openbabel openbabel
``` -->

### Dependencies

Note: make sure that all dependencies are installed through conda

```bash
conda install numpy scipy matplotlib pandas scikit-learn jupyter ipython seaborn sphinx
pip install opencv-python
pip install nni==2.3
```


#### install torch, tensorflow-gpu, transformers

Note: cuda11.1 is used (Build cuda_11.5.r11.5/compiler.30672275_0)

```bash
# conda
conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c nvidia
# pip
pip install torch==1.8.1
pip install torch==1.11.0 torchvision==0.9.1+cu111 torchaudio==0.8.1 -f https://download.pytorch.org/whl/torch_stable.html
pip install tensorflow-gpu==2.4.1
```

```bash
# wheel package install
pip install -q transformers datasets
pip install torch==1.8.1
pip install -q timm

# development installation
git clone --recursive https://github.com/huggingface/transformers.git
# checkout to specific version
git checkout v4.7.0
pip install -e .
```

#### additional libraries for training and testing

```
pip install mlflow optuna
pip install tensorboardX
```

### (Optional)

#### Install openbabel from source

```bash
cd ~/tools
wget https://github.com/openbabel/openbabel/archive/refs/tags/openbabel-3-1-1.tar.gz
tar -xzvf openbabel-3-1-1.tar.gz
cd openbabel-openbabel-3-1-1
mkdir ob-build
cd ob-build
cmake -DPYTHON_BINDINGS=ON ..
make -j
make install
```

<!-- #### Install rdkit from source

```bash
conda install -y cmake cairo pillow eigen pkg-config
conda install -y boost-cpp boost py-boost
conda install -y gxx_linux-64

cd ~/tools
git clone https://github.com/rdkit/rdkit.git
cd rdkit
mkdir build && cd build
cmake -DPy_ENABLE_SHARED=1 \
  -DRDK_INSTALL_INTREE=ON \
  -DRDK_INSTALL_STATIC_LIBS=OFF \
  -DRDK_BUILD_CPP_TESTS=ON \
  -DPYTHON_NUMPY_INCLUDE_PATH="$(python -c 'import numpy ; print(numpy.get_include())')" \
  -DBOOST_ROOT="$CONDA_PREFIX" \
  ..
make -j && make install
``` -->


# How To Use
## Install repo as development mode
```bash
pip install -e .
from .source import transformer

```

