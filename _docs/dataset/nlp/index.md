---
title: NLP Datasets
permalink: /docs/dataset/nlp
redirect_from: /docs/dataset/nlp.html
---
<hr style="border:.8px solid silver"> 
 
We describe more details about our NLP datasets. We provide realistic client mappings, and the train and val partitions of each dataset, using the following format by default: 
```
dataset/
├── client_data_mapping
│   └── *.csv for client data mapping and train/test splitting
```


Note that no details were kept of any of the participants age, gender, or location, and random ids are assigned to each individual. 


| Dataset                          | Data Type   |# of Clients  | # of Samples   | Example Task | 
|----------------------------------| ----------- | -----------  |  ----------- |   ----------- |
| [Europarl](#europarl )           |   Text      |   27,835     |   1.2M        |   Text translation
| [Blog Corpus](#blog)             |   Text      |   19,320     |   137M        |   Word prediction
| [Stackoverflow](#stack-overflow) |   Text      |   342,477    |   135M        |  Word prediction, classification
| [Reddit](#reddit)                |   Text      |  1,660,820   |   351M        |  Word prediction
| [Amazon Review](#amazon)         |   Text      | 1,822,925    |   166M        | Classification, Word prediction
| [CoQA](#coqa)                    |   Text      |     7,189    |   114K        |  Question Answering
| LibriTTS                         |   Text      |     2,456    |    37K        |   Text to speech
| [Google Speech](#speech)         |   Audio     |     2,618    |   105K        |   Speech recognition
| [Common Voice](#common-voice)    |   Audio     |     12,976   |    1.1M       |   Speech recognition


<hr style="border:.8px solid silver"> 
### Description of Datasets

---
#### Europarl

The European Parliament Proceedings Parallel Corpus is extracted from the proceedings of the European Parliament. It includes versions in 21 European languages: Romanic (French, Italian, Spanish, Portuguese, Romanian), Germanic (English, Dutch, German, Danish, Swedish), Slavik (Bulgarian, Czech, Polish, Slovak, Slovene), Finni-Ugric (Finnish, Hungarian, Estonian), Baltic (Latvian, Lithuanian), and Greek. We use French and English here.

**References**:
The original location of this dataset is available [here](https://www.statmt.org/europarl/).

---
#### Blog
The Blog Corpus Dataset consists of the collected posts of 19,320 bloggers gathered from blogger.com in August 2004. The corpus incorporates a total of 681,288 posts and over 140 million words - or approximately 35 posts and 7250 words per person.

**References**:
The original location of this dataset is at [Blog Corpus](https://www.kaggle.com/datasets/rtatman/blog-authorship-corpus).

---
#### Stack Overflow
StackOverflow.com is an online question-and-answer site for programmers. This dataset includes an archive of Stack Overflow content, including posts, votes, tags, and badges.


**References**:
This dataset is covered in more detail [here](https://www.tensorflow.org/federated/api_docs/python/tff/simulation/datasets/stackoverflow/load_data) with original [location](https://storage.googleapis.com/tff-datasets-public/stackoverflow.tar.bz2).

---
#### Reddit
This corpus contains preprocessed posts from the Reddit dataset. The dataset consists of 3,848,330 posts with an average length of 270 words for content, and 28 words for the summary.

**References**:
This dataset is covered in more detail [here](https://github.com/TalwalkarLab/leaf/tree/master/data/reddit) with original [location](https://files.pushshift.io/reddit/).

---
#### Amazon
This dataset contains product reviews and metadata from Amazon, including 142.8 million reviews spanning May 1996 - July 2014. 
It includes reviews (ratings, text, helpfulness votes), product metadata (descriptions, category information, price, brand, and image features), and links (also viewed/also bought graphs).

**References**:
The original location of this dataset is at
[Amazon Review Dataset](https://jmcauley.ucsd.edu/data/amazon/).

---
#### CoQA
CoQA is a large-scale dataset for building Conversational Question Answering systems. The goal of the CoQA challenge is to measure the ability of machines to understand a text passage and answer a series of interconnected questions that appear in a conversation.


**References**:
The original location of this dataset is at
[CoQA Dataset](https://stanfordnlp.github.io/coqa/).

---
#### Speech
This is a set of one-second .wav audio files, each containing a single spoken
English word. These words are from a small set of commands, and are spoken by a
variety of different speakers. Spoken words and speaker ids are encoded 
in each file name. If a speaker contributed multiple utterances of the same word, these are distinguished by the number at the end of the file name. For example, the file path `up_aff582a1_nohash_1.wav` indicates that the word spoken was "up", the speaker's id was "aff582a1", and this is the third utterance of that word by this speaker in the data set. 

**References**:
This dataset is covered in more detail [here](https://arxiv.org/abs/1804.03209) with original [location](http://download.tensorflow.org/data/speech_commands_v0.02.tar.gz).

---
#### Common Voice

The Common Voice dataset consists of a unique MP3 and corresponding text file. Many of the 9,283 recorded hours in the dataset also include demographic metadata like age, sex, and accent that can help train the accuracy of speech recognition engines.


**References**:
The original location of this dataset is at
[Common Voice Dataset](https://commonvoice.mozilla.org/en/datasets).
