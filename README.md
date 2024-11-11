# Deep Learning for Supervised Text Classification (Repository Currently Being Revised and Updated)
## Internship Project

![Deep Learning](https://img.shields.io/badge/Deep_Learning-Text_Classification-blue)
![Python](https://img.shields.io/badge/Python-3.6%2B-green)
![PyTorch](https://img.shields.io/badge/PyTorch-1.10.2-red)
![Transformers](https://img.shields.io/badge/Transformers-4.18.0-yellow)

## Introduction

This repository contains the work completed during my internship focusing on Deep Learning approaches for Supervised Text Classification. The project explores various neural network architectures and their effectiveness in classifying text across 24 broad semantic categories (also called supersenses).

## Project Context

This project focuses on:

- Classifying word senses with their definition and in context examples into supersenses
- Implementing and comparing different deep learning architectures
- Analyzing the impact of various text preprocessing techniques
- Evaluating model performance across different classification scenarios
- Exploring transfer learning approaches using pre-trained language models
- Exploring ensemble learning with two classifiers to achieve better results
- Building a semanticaly enriched lexical resource using the best classifier trained

## Dataset

The project utilizes the following dataset:

**Wiktionary**:

- The data collected is the word sense data from the Wiktionary. Each word sense is mainly represented by the word itself, a definition and zero to a few example sentences using the word in this sense.

- The data was extracted with a Python ETL pipeline from a dump file using RDF format of the Wiktionary. New dump files with current states of the Wiktionary are created regularly. The files can be found on the DBnary website.

- Dbnary is derived from Wiktionary and is distributed under Creative Commons Attribution-ShareAlike 3.0.

- Sérasset Gilles (2014). DBnary: Wiktionary as a Lemon-Based Multilingual Lexical Resource in RDF. to appear in Semantic Web Journal (special issue on Multilingual Linked Open Data). [pdf](http://www.semantic-web-journal.net/system/files/swj648.pdf)

## Models Implemented

The following deep learning models were implemented and evaluated:

1. **BERT-Based Models**
   - BERT contextual embedding
   - MLP with one hidden layer as classifier

2. **Llama3.2-Based Models**
   - Inference by leveraging the probability distribution of next token to be generated
   - Replacing the modeling head with a linear classifier and fine-tuning

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/NicolasAngleraud/Deep-Learning-for-Supervised-Text-Classification.git
cd Deep-Learning-for-Supervised-Text-Classification
```

2. Create a virtual environment and install dependencies:
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

3. Run the ETL data pipeline (provided one have a ttl dump file):
```bash
src/models/etl_pipeline.sh
```

4. Run the training pipeline:
```bash
src/models/train_model.sh
```

5. Run the grid search pipeline:
```bash
src/models/train_model.sh
```

6. Run the resource production pipeline:
```bash
src/models/build_resource.sh
```

## Requirements

- fr-core-news-lg @ https://github.com/explosion/spacy-models/releases/download/fr_core_news_lg-3.6.0/fr_core_news_lg-3.6.0-py3-none-any.whl
- matplotlib==3.3.4
- numpy==1.19.5
- pandas==1.1.5
- sacremoses==0.0.53
- spacy==3.6.1
- spacy-legacy==3.0.12
- spacy-loggers==1.0.5
- torch==1.10.2+cu102
- torch-scatter==2.0.9
- torchaudio==0.10.2+cu102
- torchvision==0.11.3+cu102
- transformers==4.18.0
