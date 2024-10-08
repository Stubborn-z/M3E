 <h1 align ="center"> Extractive Medical Entity Disambiguation with Memory Mechanism and Memorized entity Entity Information </h1>
Code for the paper "Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information". 
In this paper, we propose a novel approach called Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information. Specifically, we reframe MED as a text extraction task, which simultaneously accepts the entire context of medical mentions, all possible candidate entities, and entity definitions, and it is then trained to extract the text span corresponding to the correct entity.. 


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
We conduct experiments on two real-world public biomedical datasets for MED, which are MedMentions and BC5CDR. You can download the MedMentions dataset and BC5CDR dataset, then unpack it in the data folder. The original datasets can be downloaded from the following URLs.

| Dataset   |      URLs      | 
|----------|:-------------:|
| MedMentions |  https://github.com/chanzuckerberg/MedMentions  |
| BC5CDR |  http://www.biocreative.org/tasks/biocreative-v/track-3-cdr/  |

## Download BioBART model
Download the [BioBART-v2](https://github.com/GanjinZero/BioBART) model and place is under the root directory ./biobart.

## Train the M3E Model on the Dataset
If you want to train own model you just have to run the following command in the MMIE folder:
```bash
python mmie/train.py
```
If you want to evaluate the model on a dataset, just add the parameter ```--evaluate``` on the previous command.

```bash
python mmie/evaluate.py
```

## Acknowledgement

If this work is useful in your research, please cite our paper.
```bash
@inproceedings{ zhang-etal-2024-extractive,
    title = "Extractive Medical Entity Disambiguation with Memory Mechanism and Memorized Entity Information",
    author = " Guobiao Zhang, Xueping Peng, Tao Shen, Guodong Long, Jiasheng Si, Libo Qin, Wenpeng Lu",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2024",
    year = "2024",
}
```
