---
title: CV Datasets
permalink: /docs/dataset/cv
redirect_from: /docs/dataset/cv.html
---
<hr style="border:.8px solid silver"> 
 
We describe more details about our CV datasets. We provide realistic client mappings, and the train and val partitions of each dataset, using the following format by default: 
```
dataset/
├── client_data_mapping
│   └── *.csv for client data mapping and train/test splitting
```


Note that no details were kept of any of the participants age, gender, or location, and random ids are assigned to each individual. 


### Statistics of Datasets

| Dataset                       | Data Type   |# of Clients  | # of Samples   | Example Task | 
|-------------------------------| ----------- | -----------  |  ----------- |    ----------- |
| [iNature](#inaturalist)       |   Image     |   2,295      |   193K        |   Classification
| [FMNIST](#femnist)            |   Image     |   3,400      |   640K        |   Classification
| [OpenImage](#openimage)       |   Image     |   13,771     |   1.3M        |   Classification, Object detection
| [Google Landmark](#landmark)  |  Image     |   43,484     |   3.6M        |   Classification
| Charades                      |   Video     |    266       |   10K         |   Action recognition
| VLOG                          |   Video     |    4,900     |   9.6k        |   Video classification, Object detection
| [Waymo Motion](#waymo-motion) | Video       | 496,358      | 32.5M         | Motion prediction


<hr style="border:.8px solid silver"> 
### Description of Datasets

---
#### iNaturalist
The iNaturalist 2019 at FGVC6 dataset contains 1,010 species, with a combined training and validation set of 268,243 images that have been collected and verified by multiple users from iNaturalist.

**References**:
The original location of this dataset is available [here](https://sites.google.com/view/fgvc6/competitions/inaturalist-2019).



---
#### FEMNIST
FEMNIST has 62 different classes (10 digits, 26 lowercase, 26 uppercase) across 3600 users. Images are 28 by 28 pixels (with option to make them all 128 by 128 pixels). 

**References**:
The original location of this dataset is available [here](https://www.nist.gov/srd/nist-special-database-19).


---
#### Open Images
Open Images V5 is a dataset of ~9M images annotated with image-level labels, object bounding boxes, object segmentation masks, and visual relationships.

**References**:
The original location of this dataset is available [here](https://storage.googleapis.com/openimages/web/download_v5.html).


---
#### Landmark
The Google Landmark Dataset contains images annotated with labels representing human-made and natural landmarks. 
The dataset can be used for landmark recognition and retrieval experiments.

**References**:
The dataset was presented in [CVPR'20](https://arxiv.org/abs/2004.01804) and [Google AI blog post](https://ai.googleblog.com/2019/05/announcing-google-landmarks-v2-improved.html).

---
#### Waymo Motion
Waymo Motion Dataset is composed of 103,354 segments each containing 20
seconds of object tracks at 10Hz and map data for the area covered by the segment. These segments
are further broken into 9 second scenarios (8 seconds of future data and 1 second of history) with 5
second overlap, and we consider each scenario as a client.


**References**:
The original location of this dataset is at [Waymo Motion](https://waymo.com/intl/en_us/dataset-motion/).

