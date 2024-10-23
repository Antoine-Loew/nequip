## NequIP-2FC

This is a modified NequIP version designed to train on the force constants used in our article [1](https://iopscience.iop.org/article/10.1088/2632-2153/ad86a1/meta). It uses version 0.5.1 of NequIP [2](https://www.nature.com/articles/s41467-022-29939-5).

The models trained on LiBC and TiNbTa, as discussed in the article, can be found [here](https://github.com/hyllios/utils/tree/main/models/nequip-2fc).

## Installation

NequIP requires:

* Python >= 3.7, <=3.9.*
* PyTorch >= 1.8, !=1.9, <=1.11.*. PyTorch can be installed following the [instructions from their documentation](https://pytorch.org/get-started/locally/). Note that neither `torchvision` nor `torchaudio`, included in the default install command, are needed for NequIP.

To install:

* [Weights&Biases](https://wandb.ai) can be used to keep track of experiments. This is not a strict requirement — you can use our package without it — but it may make your life easier. If you want to use it, create an account [here](https://wandb.ai) and install the Python package:

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

Using the newly implemented output layer called 'ForceConstantOutput', you can build a model that enables training on force constants. To do so, several conditions need to be met:

- The input structures must be the supercells on which the phonon calculations were performed.

- The s2u key from phonopy must be provided in the extxyz format, this determined the indices of unitcell's atoms inside the supercell .

- The reduced force constants must be provided in the extxyz format in the same order as in Phonopy. They should be reshaped along the first dimension to obtain a shape of (n*N, 3, 3), where n is the number of atoms in the unit cell, N is the number of atoms in the supercell, and the last two indices correspond to the Cartesian coordinates.

You can find two folders corresponding to the two structures in the examples/phonon_train/ directory. For example, to start training on TiNbTa, go inside the folder examples/phonon_train/TiNbTa and use:

```
nequip-train config_TiNbTa_base.yaml
```




## References & Citation

The theory behind NequIP is described in the preprint [2]. NequIP's backend builds on **e3nn**, a general framework for building E(3)-equivariant neural networks [3]. If you use this fork in your work, please consider citing NequIP-2FC [1], NequIP [2], and e3nn [4]:

 1. https://iopscience.iop.org/article/10.1088/2632-2153/ad86a1/meta
 2. https://www.nature.com/articles/s41467-022-29939-5
 3. https://e3nn.org
 4. https://doi.org/10.5281/zenodo.3724963