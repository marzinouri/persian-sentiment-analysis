# Persian Sentiment Analysis Project

This repository contains code and data for a Persian sentiment analysis project, which aims to analyze the sentiment of news articles in Persian text. The project involves balancing the dataset using both downsampling and upsampling techniques with back translation. It also includes data preprocessing steps and fine-tuning of the ParsBERT model for sentiment analysis.

## Dataset

The dataset used in this project consists of 1600 news articles that have been annotated by three different individuals. The dataset includes three sentiment labels: positive, negative, and neutral. To ensure data quality and disambiguation, a maximum vote approach has been used.

### Dataset Versions

1. **Original Dataset**: This is the raw dataset containing 1600 entries of news articles annotated by three people.

2. **Downsampled Dataset**: In this version, the dataset has been balanced by downsampling, resulting in 400 entries for each sentiment class (positive, negative, and neutral).

3. **Upsampled Dataset with Back Translation**: This version of the dataset has been balanced by upsampling using a back translation technique, resulting in 608 entries for each sentiment class.

## Data Preprocessing

Before fine-tuning the model, the dataset has undergone several preprocessing steps to clean and prepare the text data for analysis. The following preprocessing steps have been applied:

- Removal of special characters
- Removal of HTML tags
- Removal of URLs
- Conversion of Arabic/Persian numbers to English numbers
- Removal of references like [1]
- Removal of English characters (if any)

## Fine-Tuning ParsBERT

ParsBERT, a pre-trained transformer-based model for Persian text, has been fine-tuned for sentiment analysis using the preprocessed dataset. A total of 18 experiments have been performed on three different dataset versions. The best result was achieved on the downsampled dataset, with an F1 score of 0.735.

### Experiment Details

| #  | Dataset Type   | Num of Epochs | Learning Rate | Batch Size | F1 Score |
|----|----------------|---------------|---------------|------------|----------|
| 1  | Downsampled    | 3             | 1e-5          | 16         | 0.735    |
| 2  | Downsampled    | 5             | 1e-5          | 16         | 0.690    |
| 3  | Downsampled    | 7             | 1e-5          | 16         | 0.637    |
| 4  | Downsampled    | 3             | 2e-5          | 16         | 0.676    |
| 5  | Downsampled    | 5             | 2e-5          | 16         | 0.651    |
| 6  | Downsampled    | 7             | 2e-5          | 16         | 0.592    |
| 7  | Upsampled      | 3             | 1e-5          | 16         | 0.660    |
| 8  | Upsampled      | 5             | 1e-5          | 16         | 0.633    |
| 9  | Upsampled      | 7             | 1e-5          | 16         | 0.693    |
| 10 | Upsampled      | 3             | 2e-5          | 16         | 0.673    |
| 11 | Upsampled      | 5             | 2e-5          | 16         | 0.626    |
| 12 | Upsampled      | 7             | 2e-5          | 16         | 0.589    |
| 13 | Original       | 3             | 1e-5          | 16         | 0.640    |
| 14 | Original       | 5             | 1e-5          | 16         | 0.578    |
| 15 | Original       | 7             | 1e-5          | 16         | 0.694    |
| 16 | Original       | 3             | 2e-5          | 16         | 0.607    |
| 17 | Original       | 5             | 2e-5          | 16         | 0.669    |
| 18 | Original       | 7             | 2e-5          | 16         | 0.685    |


The best result was achieved on the downsampled dataset (#1 experiment) with 3 epochs, a learning rate of 1e-5, and a batch size of 16, resulting in an F1 score of 0.735.

## Files

- `back_trans_fa_en_fa.json`: Upsampled data with back translation technique.
- `down_sampled.json`: Downsampled data.
- `dataset_annotated_sentiment.json`: Original annotated data.
- `downsampled-minimalReportIncluded.ipynb`: Jupyter Notebook containing code for fine-tuning ParsBERT on the downsampled dataset, including a minimal report in Persian.
- `upsampled.ipynb`: Jupyter Notebook containing code for fine-tuning ParsBERT on the upsampled dataset.
