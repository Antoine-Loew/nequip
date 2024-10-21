## NequIP-2FC

This is a modified NequIP version designed to train on the force constants used in our article [1](https://iopscience.iop.org/article/10.1088/2632-2153/ad86a1/meta). It uses version 0.5.1 of NequIP [2](https://www.nature.com/articles/s41467-022-29939-5).

The models trained on LiBC and TiNbTa, as discussed in the article, can be found [here](https://github.com/hyllios/utils/tree/main/models/nequip-2fc).

## Installation

NequIP requires:

* Python >= 3.7
* PyTorch >= 1.8, !=1.9, <=1.11.*. PyTorch can be installed following the [instructions from their documentation](https://pytorch.org/get-started/locally/). Note that neither `torchvision` nor `torchaudio`, included in the default install command, are needed for NequIP.

To install:

* We use [Weights&Biases](https://wandb.ai) to keep track of experiments. This is not a strict requirement — you can use our package without it — but it may make your life easier. If you want to use it, create an account [here](https://wandb.ai) and install the Python package:

  ```
  pip install wandb
  ```

* Install NequIP-2FC

  From source:
  ```
  git clone https://github.com/Antoine-Loew/nequip
  cd nequip
  pip install . 
  ```


## Training phonon 

\



## References & Citation

The theory behind NequIP is described in the preprint [2]. NequIP's backend builds on **e3nn**, a general framework for building E(3)-equivariant neural networks [3]. If you use this fork in your work, please consider citing NequIP-2FC [1], NequIP [2], and e3nn [4]:

 1. https://iopscience.iop.org/article/10.1088/2632-2153/ad86a1/meta
 2. https://www.nature.com/articles/s41467-022-29939-5
 3. https://e3nn.org
 4. https://doi.org/10.5281/zenodo.3724963