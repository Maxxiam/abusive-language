# Abusive Language

## Requirements
- python 3.4
- tensorflow 1.0
- keras 2.0 (for tf model layer construction)
- numpy
- sklearn (for splitting dataset)
- nltk (for ngram)
- pandas (for loading csv)
- re (for regex)
- jupyter notebook (for debugging) 
- tqdm (for displaying process)
- pickle (for saving python object)

## Scripts
- To run ngram logistic regression classifier:
    1. `preprocess_ngram_lr.py` 
        a. load the unshared task data, preprocess the tweets, and put it in one
        b. make two binary datasets (`racism_binary`, `sexism_binary`)
        c. split the dataset into train/valid/test and save into file (`/data/preprocessed`)
        d. create a ngram dictionary from train dataset 
        e. turn tweets into ngram feature dataset and save to files (`/data/ngram_outputs`)
    2. `train_ngram_lr.py`
        - train the logistic regression model

## Modules
### data
- `preprocess.py`: clean the tweet
- `tokenizer.py`: tokenize text into characters/words
- `ngrams.py`: make text into ngram features
- `utils.py`: helpers related to dataset (splitting, batch generation)

### model
- `lr.py`: linear regression model
- `char_cnn.py`: character-level convolutional neural network

## See run results from Tensorboard
- after each run, the logs will be saved at `/logs/`. check command line log for the exact directory
- run `tensorboard --logdir=/logs/xxxxxx`
- if using remote server, ssh with portforwarding -L option. ex. `ssh -L 16006:127.0.0.1:6006 jhpark@remoteserver.hk` This option will forward remote 6006 port (default port for tensorboard) to localhost 16006.

## Notebooks
- `unshared_task_analysis/ipynb`: analysis of the Hate Speech Dataset

## Datasets
1. `Hate Speech Dataset`: see `original/README.md`

## Python Style Guide
Please follow PEP 8.
https://www.python.org/dev/peps/pep-0008/
https://realpython.com/blog/python/vim-and-python-a-match-made-in-heaven/
