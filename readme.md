# Code Summarization using Transformer Model
This repo provides code to train an Encoder-Decoder type Transformer model for code summarization on the [CodeSearchNet](https://arxiv.org/abs/1909.09436) dataset.

In my experiments the model was trained on NVIDIA A100 GPU- 40GB  in Google Colab Platform. 

Note: The model was trained on the `python` subset of the dataset.

## Dependencies
- pip install pytorch-ignite
- python -m spacy download en_core_web_sm
- pip install portalocker==2.1

## Dataset
The dataset used is the [CodeSearchNet](https://arxiv.org/abs/1909.09436), which comprises 6 million functions from open source code. It is divided into six languages: `python`, `java`, `javascript`, `php`, `ruby` and `go`. Furthermore, the dataset is split into three parts: `train`, `valid` and `test`. The dataset is available in the `JSONL` format.


## Dataset Download
You can download dataset from the google drive [link](https://drive.google.com/uc?id=1rd2Tc6oUWBo7JouwexW3ksQ0PaOhUr6h), or use the following command.

```bash
pip install gdown
mkdir data data/code2nl
cd data/code2nl
gdown https://drive.google.com/uc?id=1rd2Tc6oUWBo7JouwexW3ksQ0PaOhUr6h
unzip Cleaned_CodeSearchNet.zip
rm Cleaned_CodeSearchNet.zip
cd ../..
```

## Training the model
To train the model, with the hyper-parameters used in the code, run the cells on an instance with A100 GPU. The model will be saved in the `model_saves` folder.

Before running the cells, make sure to change the `file_path` variable to the path where the dataset is stored, and the `model_filepath` variable to the directory where the model is to be saved.

The model hyper-parameters can be adjusted to experiment with various configurations, depending on the available hardware.