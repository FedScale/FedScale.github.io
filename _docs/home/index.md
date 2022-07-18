---
title: Get Started
permalink: /docs/home/
redirect_from: /docs/index.html
---
<hr style="border:.8px solid silver">


### Overview
FedScale is a scalable and extensible open-source federated learning (FL) system. It provides high-level APIs to implement FL algorithms, deploy them at scale across diverse hardware and software backends, and evaluate them at scale. FedScale also includes the largest <a href="">FL benchmark</a> that contains FL tasks ranging from image classification and object detection to language modeling and speech recognition. Moreover, it provides datasets to faithfully emulate FL training environments where FL will realistically be deployed.

<hr style="border:.8px solid silver">

### Package Installation

We next show how to install FedScale after cloning it from [source](https://github.com/symbioticlab/fedscale). 

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

Finally, install NVIDIA [CUDA 10.2](https://developer.nvidia.com/cuda-downloads) or above if you want to use FedScale with GPU support.

Next, let us play with it to submit jobs or implementing your FL work in a few lines of code.
- [Submit your first job]({{ "/docs/tutorial/deployment/"  | relative_url }})
- [Implement new FL algorithms]({{ "/docs/tutorial/customization/"  | relative_url }})

<hr style="border:.8px solid silver">
### References
Please read and/or cite as appropriate to use FedScale code or data or learn more about FedScale.

```bibtex
@inproceedings{fedscale-icml22,
  title={FedScale: Benchmarking Model and System Performance of Federated Learning at Scale},
  author={Fan Lai and Yinwei Dai and Sanjay S. Singapuram and Jiachen Liu and Xiangfeng Zhu and Harsha V. Madhyastha and Mosharaf Chowdhury},
  booktitle={International Conference on Machine Learning (ICML)},
  year={2022}
}
```

and  

```bibtex
@inproceedings{oort-osdi21,
  title={Oort: Efficient Federated Learning via Guided Participant Selection},
  author={Fan Lai and Xiangfeng Zhu and Harsha V. Madhyastha and Mosharaf Chowdhury},
  booktitle={USENIX Symposium on Operating Systems Design and Implementation (OSDI)},
  year={2021}
}
```