---
title: Misc Datasets
permalink: /docs/dataset/misc
redirect_from: /docs/dataset/misc.html
---
<hr style="border:.8px solid silver"> 
 
We describe more details about many other federated learning datasets. We provide realistic client mappings, and the train and val partitions of each dataset, using the following format by default: 
```
dataset/
├── client_data_mapping
│   └── *.csv for client data mapping and train/test splitting
```


Note that no details were kept of any of the participants age, gender, or location, and random ids are assigned to each individual. 


| Dataset                                        | Data Type   |# of Clients  | # of Samples   | Example Task | 
|------------------------------------------------| ----------- | -----------  |  ----------- |   ----------- |
| [Taxi Trajectory](#taxi-trajectory-prediction) |   Text      |      442     |    1.7M       |   Sequence Prediction
| [Puffer](#puffer)                              |   Text      |     121,551  |   15.4M       |   Sequence Prediction
| [Taobao](#taobao)                              |   Text      |     182,806  |    0.9M       |   Recommendation
| Go dataset                                     |   Text      |     150,333  |    4.9M       |   Reinforcement learning


<hr style="border:.8px solid silver"> 
### Description of Datasets

---
#### Taxi Trajectory Prediction
This dataset describes a complete year (from 01/07/2013 to 30/06/2014) of the trajectories for all the 442 taxis (clients) running in the city of Porto, in Portugal. 
In this task, we may build a predictive framework that is able to infer the final destination of taxi rides based on their (initial) partial trajectories. Details of features are available [here](https://www.kaggle.com/c/pkdd-15-predict-taxi-service-trajectory-i/overview).

**References**:
The original location of this dataset is at [ECML/PKDD 15: Taxi Trajectory Prediction](https://www.kaggle.com/c/pkdd-15-predict-taxi-service-trajectory-i/overview).

---
#### Puffer
Puffer data comprises different measurements of the Internet network bandwidth in video streaming — each measurement contains a different set of time-series data collected on Puffer servers, and is dumped as a CSV file. We select the data of the first week data of 2021. 

**References**:
The original location of this dataset is at [Puffer Dataset](https://puffer.stanford.edu/data-description/).

---
#### Taobao

Taobao Ali_Display_Ad_Click is a dataset of click rate prediction about display Ad, which is displayed on the website of Taobao. The dataset is offered by the company of Alibaba. 

**References**:
The original location of this dataset is available [here](https://tianchi.aliyun.com/dataset/dataDetail?dataId=56).
