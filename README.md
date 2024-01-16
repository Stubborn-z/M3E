 <h1 align ="center"> Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information </h1>
Code for the paper "Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information". \
In this paper, we propose a novel approach called Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information (MMIE). Specifically, we reframe MED as a text extraction task, which simultaneously accepts the entire context of medical mentions, all possible candidate entities and entity definitions, and is trained to extract the text span corresponding to the correct entity. 


![](data/repo-assets/model.png)
## Setup

Requirements:
* Debian-based (e.g. Debian, Ubuntu, ...) system 
* [conda](https://docs.conda.io/en/latest/) installed

Run the following command to quickly setup the env needed to run our code:
```bash
bash setup.sh
```

## Data Preparation
We conduct experiments on two real-world public biomedical datasets for MED, which are MedMentions and BC5CDR. You can download the MedMentions dataset [[here](https://github.com/chanzuckerberg/MedMentions)]and BC5CDR dataset [[here](http://www.biocreative.org/tasks/biocreative-v/track-3-cdr/)], then unpack it in the data folder.

## Download BioBART model
Download the [BioBART-v2](https://github.com/GanjinZero/BioBART) model and place is under the root directory ./biobart.

## Train the WSD Model on the Dataset
If you want to train own model you just have to run the following command in the MMIE folder:
```bash

```
If you want to evaluate the model on a dataset, just add the parameter ```--evaluate``` on the previous command.

```
## Citation
Please cite our paper if you find it helpful.

