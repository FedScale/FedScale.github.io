---
title: FedScale Datasets
permalink: /docs/dataset
redirect_from: /docs/dataset.html
---
<hr style="border:.8px solid silver">


### Overview

Realistic FL evaluation requires careful dataset selection and environment setup.
As such, FedScale provides two categories of datasets:

1. [Workload datasets](##workload-datasets) that represent diverse FL tasks; and
2. [Environment datasets](##environment-datasets) that reflect settings FL will be deployed.

When running in the benchmark evaluation mode, FedScale runtime can leverage the latter to evaluate the former in realistic settings.

### Download

You can use `download.sh` to download individual datasets. 

```
# Run download.sh --help for more details
bash download.sh -dataset_name
```

<hr style="border:.8px solid silver">

### Workload Datasets Details

***We are continuously adding more datasets! Please contribute.***

We provide real-world datasets for the federated learning community, and plan to release much more soon! 
Each one is associated with its training, validation and testing dataset. 
A summary of statistics for training datasets can be found in the table below, and you can refer to each folder for more details. 

You can use [this example code](https://github.com/SymbioticLab/FedScale/blob/master/docs/Femnist_stats.md) to explore any of the FedScale datasets. 

---

#### CV Tasks

| Dataset       | Data Type   |# of Clients  | # of Samples   | Example Task | 
| -----------   | ----------- | -----------  |  ----------- |    ----------- |
| iNature       |   Image     |   2,295      |   193K        |   Classification
| FMNIST        |   Image     |   3,400      |   640K        |   Classification
| OpenImage     |   Image     |   13,771     |   1.3M        |   Classification, Object detection
| Google Landmark|  Image     |   43,484     |   3.6M        |   Classification
| Charades      |   Video     |    266       |   10K         |   Action recognition
| VLOG          |   Video     |    4,900     |   9.6k        |   Video classification, Object detection
| Waymo Motion  | Video       | 496,358      | 32.5M         | Motion prediction

---
#### NLP Tasks

| Dataset       | Data Type   |# of Clients  | # of Samples   | Example Task | 
| -----------   | ----------- | -----------  |  ----------- |   ----------- |
| Europarl      |   Text      |   27,835     |   1.2M        |   Text translation
| Blog Corpus   |   Text      |   19,320     |   137M        |   Word prediction
| Stackoverflow |   Text      |   342,477    |   135M        |  Word prediction, classification
| Reddit        |   Text      |  1,660,820   |   351M        |  Word prediction
| Amazon Review |   Text      | 1,822,925    |   166M        | Classification, Word prediction
| CoQA          |   Text      |     7,189    |   114K        |  Question Answering
| LibriTTS      |   Text      |     2,456    |    37K        |   Text to speech
| Google Speech |   Audio     |     2,618    |   105K        |   Speech recognition
| Common Voice  |   Audio     |     12,976   |    1.1M       |   Speech recognition

---
#### Misc Applications

| Dataset       | Data Type   |# of Clients  | # of Samples   | Example Task | 
| -----------   | ----------- | -----------  |  ----------- |   ----------- |
|Taxi Trajectory|   Text      |      442     |    1.7M       |   Sequence Prediction
| Puffer        |   Text      |     121,551  |   15.4M       |   Sequence Prediction
| Taobao        |   Text      |     182,806  |    0.9M       |   Recommendation
| Go dataset    |   Text      |     150,333  |    4.9M       |   Reinforcement learning

***Note that no details were kept of any of the participants age, gender, or location, and random ids were assigned to each individual. In using these datasets, we will strictly obey to their licenses, and these datasets provided in this repo should be used for research purpose only.***

<hr style="border:.8px solid silver">
### Environment Datasets

One of the key challenges in FL is reproducing the environment where FL will likely be deployed. 
To this end, we provide environmental datasets to reproduce heterogeneous device performance and device availability traces. 

- ***Heterogeneous System Performance***: We use the [AIBench](http://ai-benchmark.com/ranking_deeplearning_detailed.html) dataset and [MobiPerf](https://www.measurementlab.net/tests/mobiperf/) dataset. 
AIBench dataset provides the computation capacity of different models across a wide range of devices. 
As specified in real [FL deployments](https://arxiv.org/abs/1902.01046), we focus on the capability of mobile devices that have > 2GB RAM in this benchmark. 
To understand the network capacity of these devices, we clean up the MobiPerf dataset, and provide the available bandwidth when they are connected with WiFi, which is preferred in FL as well. 

- ***Availability of Clients***: We use a large-scale real-world user behavior dataset from [FLASH](https://github.com/PKU-Chengxu/FLASH). 
It comes from a popular input method app (IMA) that can be downloaded from Google Play, and covers 136k users and spans one week from January 31st to February 6th in 2020. 
This dataset includes 180 million trace items (e.g., battery charge or screen lock) and we consider user devices that are in charging to be available, as specified in real [FL deployments](https://arxiv.org/abs/1902.01046).


