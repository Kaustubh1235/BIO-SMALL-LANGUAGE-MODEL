BioGPT Language Model for Biomedical Text
This project focuses on the pre-training and fine-tuning of a GPT-style language model, BioGPT, for tasks in the biomedical domain. The model is trained on a large-scale dataset of biomedical literature and then fine-tuned for a specific downstream task: classifying the Hallmarks of Cancer.

Table of Contents
Project Overview

Getting Started

Prerequisites

Installation

Usage

Pre-training

Fine-tuning

Dataset

Model Architecture

Evaluation

Project Overview
This project demonstrates the process of building a specialized language model for the biomedical field. It involves two main stages:

Pre-training: The model is trained on a large corpus of biomedical text from PubMed to learn the language and patterns of the domain.

Fine-tuning: The pre-trained model is then adapted for a specific classification task, identifying the Hallmarks of Cancer in biomedical abstracts.

Getting Started
Prerequisites
Python 3.x

PyTorch

sacremoses

scikit-learn

pandas

numpy

tqdm

lxml

beautifulsoup4

Installation
Clone the repository:

git clone https://github.com/your-username/biogpt-project.git
cd biogpt-project

Install the required packages:

pip install -r requirements.txt

Usage
Pre-training
Download the dataset: The notebook includes scripts to download and preprocess a subset of PubMed abstracts.

Prepare the data: The raw XML data is converted to plain text, and then tokenized using BPE (Byte Pair Encoding).

Train the model: The fairseq library is used to pre-train the BioGPT model on the prepared dataset.

Fine-tuning
Load the pre-trained model: The fine-tuning process starts with loading the weights of the pre-trained BioGPT model.

Prepare the HoC dataset: The Hallmarks of Cancer (HoC) dataset is loaded and preprocessed for the classification task.

Fine-tune the model: The model is fine-tuned on the HoC dataset to classify biomedical abstracts based on the hallmarks of cancer.

Dataset
Pre-training: A 10 GB subset of PubMed baseline XML files is used for pre-training.

Fine-tuning: The Hallmarks of Cancer (HoC) dataset is used for the classification task. This dataset consists of biomedical abstracts annotated with one or more of the ten hallmarks of cancer.

Model Architecture
The model is a GPT-style transformer with the following architecture:

Vocabulary Size: 42,380

Block Size: 128

Number of Layers: 6

Number of Heads: 6

Embedding Dimension: 384

Dropout: 0.1

Evaluation
The fine-tuned model is evaluated on the HoC test set. The performance is measured using micro and macro precision, recall, and F1-score.
