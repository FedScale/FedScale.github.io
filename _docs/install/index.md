---
title: Quick Start
permalink: /docs/install/
redirect_from: /docs/index.html
---
<hr style="border:.8px solid silver">

In this quick start guide, you can learn how to install FedScale after cloning it from [source](https://github.com/symbioticlab/fedscale). 

#### Quick Installation (Linux)

You can simply run `install.sh`.

```
source install.sh # Add `--cuda` if you want CUDA 
pip install -e .
```

Update `install.sh` if you prefer different versions of conda/CUDA.

#### Installation from Source (Linux/MacOS)

If you have [Anaconda](https://www.anaconda.com/products/distribution#download-section) installed and cloned FedScale, here are the instructions.
```
cd FedScale

# Please replace ~/.bashrc with ~/.bash_profile for MacOS
echo export FEDSCALE_HOME=$(pwd) >> ~/.bashrc 
echo alias fedscale=\'bash $FEDSCALE_HOME/fedscale.sh\' >> ~/.bashrc 
conda init bash
. ~/.bashrc

conda env create -f environment.yml
conda activate fedscale
pip install -e .
```

Please remember to install NVIDIA [CUDA 10.2](https://developer.nvidia.com/cuda-downloads) or above if you want to use FedScale with GPU support.

<hr style="border:.8px solid silver">

#### What's Next?
Try out the following tutorials to submit your first FedScale jobs on your laptop or in GPU a cluster, or even implement your own FL algorithms in FedScale with a few lines of code.
- [Submit your first job]({{ "/docs/tutorial/deployment/"  | relative_url }})
- [Implement new FL algorithms]({{ "/docs/tutorial/customization/"  | relative_url }})
