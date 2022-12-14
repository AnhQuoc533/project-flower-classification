# FLOWER CLASSIFIER PROJECT
This repository contains my submissions for the final project of [AI Programming with Python Nanodegree Program](https://www.udacity.com/course/ai-programming-python-nanodegree--nd089). The purpose of this project is to build, train and implement an image classifier that recognizes different species of flowers using **PyTorch**. The project is broken down into two parts: developing the classifier in Jupyter Notebook and then building the command line application for the classifier.

To successfully run the project, please install all required packages listed in [requirements.txt](requirements.txt). However, the following command line will help install the packages according to the configuration file conveniently:
```
pip -r requirements.txt
```
Additionally, please keep all files intact to avoid error.

&nbsp;
## Part 1: Developing classifier in Jupyter Notebook
---
The image classifier is built and trained step by step with a thorough instruction in [Image Classifier Project.ipynb](Image%20Classifier%20Project.ipynb).

&nbsp;
## Part 2: Building the command line application
---
This is the main part of the project. The code written in Part 1 is used as part of the application for the classifier. 

The application consists of two main files: `train.py` and `predict.py`. The first file trains a new neural network model on a dataset and saves the model as a checkpoint. The second file uses a trained model to predict the species of an input image of flower.

Usage:

1. `train.py`:
    ```
    py train.py [-h] [--save_dir [SAVE_DIR]] [--arch {vgg11,vgg13,vgg16,vgg19}] [--learning_rate ALPHA] [--hidden_units [HIDDEN_UNITS ...]] [--epochs EPOCHS] [--batch_size BATCH_SIZE] [--drop_p P] [--gpu] data_dir
    ```
* Positional arguments:
    * `data_dir`: Input directory which contains two sub-folders of dataset: _train_ and _val_.

* Optional arguments:
    * `-h, --help`: Show help message and exit
    * `--save_dir [SAVE_DIR]`: Input directory where information of trained model will be saved. No argument means saving at the current working directory.
    * `--arch {vgg11,vgg13,vgg16,vgg19}`: Choose a VGG model architecture. Default is vgg19.
    * `--learning_rate ALPHA`: Set learning rate value. Default is 0.001.
    * `--hidden_units [HIDDEN_UNITS ...]`: Input multiple integers separated by a single space to design the hidden layers for the classification part of the model.
    * `--epochs EPOCHS`: Set the number of epochs. Default is 10.
    * `--batch_size BATCH_SIZE`: Set the size of each batch. Default is 32.
    * `--drop_p P`: Set probability for dropout regularization. Default is 0.
    * `--gpu`: Allow the program to use GPU to train the model. No arguments needed.

&nbsp;

2. `predict.py`:
    ```
    py predict.py [-h] [--topk K] [--category_names JSON] [--gpu] img_path checkpoint
    ```
* Positional arguments:
    * `img_path`: Input the path to the image which will be predicted by the model.
    * `checkpoint`: Input the path to the checkpoint file which contains trained model's information.

* Optional arguments:
    * `-h, --help`: Show help message and exit
    * `--topk K`: Input the number of top classes to be displayed. Default is 3.
    * `--category_names JSON`: Input the path to the JSON file which is a mapping of categories to real name of flowers.
    * `--gpu`: Allow the program to use GPU to perform prediction. No arguments needed.