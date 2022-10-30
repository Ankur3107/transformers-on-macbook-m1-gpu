# transformers-on-macbook-m1-gpu

# Install Pytorch for Macbook M1 GPU

##  Step 1: Install Xcode
    $ xcode-select --install

##  Step 2: Setup a new conda environment
    $ conda create -n torch-gpu python=3.8
    $ conda activate torch-gpu

##  Step 3: Install Pytorch
    conda install pytorch torchvision torchaudio -c pytorch-nightly

    # If not working with conda then try pip
    pip3 install --pre torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/nightly/cpu

## Step 4: Sanity Check

```python
import torch
import math
# this ensures that the current MacOS version is at least 12.3+
print(torch.backends.mps.is_available())
# this ensures that the current current PyTorch installation was built with MPS activated.
print(torch.backends.mps.is_built())
```

# Hugging Face transformers Installation

## Step 1: Install Rust

    curl — proto ‘=https’ — tlsv1.2 -sSf https://sh.rustup.rs | sh

## Step 2: Install transformers

    pip install transformers

# Reference

1. https://pytorch.org
2. https://towardsdatascience.com/installing-pytorch-on-apple-m1-chip-with-gpu-acceleration-3351dc44d67c
3. https://jamescalam.medium.com/hugging-face-and-sentence-transformers-on-m1-macs-4b12e40c21ce