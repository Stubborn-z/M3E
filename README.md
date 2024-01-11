# Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information
Code for the paper "Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information". In this paper, we propose a novel approach called Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information (MMIE). Specifically, we reframe MED as a text extraction task, which simultaneously accepts the entire context of medical mentions, all possible candidate entities and entity definitions, and is trained to extract the text span corresponding to the correct entity.

## Environment Setup
```bash
- numpy=1.23.5
- pandas=2.0.2
- python=3.8
- pytorch=1.9.0
- scikit-learn=1.2.2
- scipy=1.10.1
- tqdm=4.65.0
- transformers=4.2.0
```

## Download BioBART model
Download the BioART v1.1 model and place is under the root directory ./biobart.

## Train the WSD Model on the Dataset
If you want to train own model you just have to run the following command in the MMIE folder:
```bash

```
If you want to evaluate the model on a dataset, just add the parameter ```--evaluate``` on the previous command.

## Training
If you want to train your own escher model you just have to run the following command:
```bash
PYTHONPATH=$(pwd) python esc/train.py --run_name fresh_escher_model --add_glosses_noise --train_path data/WSD_Evaluation_Framework/Training_Corpora/SemCor/semcor.data.xml
```

All the hyperparameters are set by default to the ones utilized in the paper. If you want to 
list them all just execute:
```bash
PYTHONPATH=$(pwd) python esc/train.py -h
```

To parse the hyperparameters in input we use [argparse](https://docs.python.org/3/library/argparse.html),
so it is very simple to change them. For example to modify the learning rate to 0.0005 and the gradient 
accumulation steps to 10 you can execute the following command:
```bash
PYTHONPATH=$(pwd) python esc/train.py --learning_rate 0.0005 --gradient_acc_steps 10 --run_name fresh_escher_model --add_glosses_noise --train_path data/WSD_Evaluation_Framework/Training_Corpora/SemCor/semcor.data.xml
```

## How to Cite
```bash

```
