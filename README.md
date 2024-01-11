# Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information
Code for the paper "Extractive Medical Entity Disambiguation with Memory Mechanism and Identified Entity Information". In this paper, we propose a novel approach called Extractive Medical Entity Disambiguation with \textbf{M}emory \textbf{M}echanism and \textbf{I}dentified \textbf{E}ntity Information (\textbf{MMIE}). Specifically, we reframe MED as a text extraction task, which simultaneously accepts the entire context of medical mentions, all possible candidate entities and entity definitions, and is trained to extract the text span corresponding to the correct entity.

## Environment Setup
To set up the python environment for this project, we strongly suggest using the bash script ```setup.sh``` that 
you can find at top level in this repo. This script will create a new conda environment and take care of all
the requirements and the data needed for the project. Simply run on the command line:
```bash
bash ./setup.sh
```
and follow the instructions.

## Prediction and Evaluation
You can disambiguate a corpus using the script ```esc/predict.py```:
```bash
PYTHONPATH=$(pwd) python esc/predict.py --ckpt <escher_checkpoint.ckpt> --dataset-paths data/WSD_Evaluation_Framework/Evaluation_Datasets/semeval2007/semeval2007.data.xml --prediction-types probabilistic
```

Where the dataset-paths that you provide to the model must be in a format that follows the one introduced by [Raganato et al. (2017)](https://www.aclweb.org/anthology/E17-1010/).
For reference, all the datasets in the directory ```data/WSD_Evaluation_Framework``` follow this format.
The predictions will be saved in the folder ```predictions``` with the name ```<dataset_name>_predictions.txt```.

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
```

```
