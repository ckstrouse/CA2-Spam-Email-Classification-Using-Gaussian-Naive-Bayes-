# CA2-Spam-Email-Classification-Using-Gaussian-Naive-Bayes-
Spam Email Classification Using Gaussian Naive Bayes
Overview

This project implements a spam email classification system using the Gaussian Naive Bayes algorithm. The notebook follows the structure and logic provided in the CA02 assignment and reproduces the expected output by applying probabilistic classification to email text data.

The model distinguishes between spam and non-spam emails by analyzing word frequency patterns extracted from email content.

Project Objective

The objective of this assignment is to understand and implement a complete text classification workflow using Naive Bayes. This includes reading and preprocessing raw email files, extracting numerical features from text, training a classifier on labeled data, and evaluating model performance on unseen test emails.

The implementation prioritizes reproducing the reference notebook behavior rather than optimizing or modifying the model.

Dataset Organization

The dataset consists of two folders:

train-mails: used to train the model

test-mails: used to evaluate the trained model

Each email is stored as a plain text file. The first two lines of each email contain header information. Only the content starting from the third line onward is used for dictionary creation and feature extraction.

Spam and non-spam labels are determined by the email filenames:

Files beginning with spmsg are labeled as spam

All other files are labeled as non-spam

The folder names and file names must remain unchanged for the notebook to run correctly.

Dictionary Creation

The notebook builds a dictionary by scanning all training emails and collecting words from the email body (excluding the first two header lines). Words are split by whitespace, and basic cleaning is applied by removing non-alphabetic tokens and single-character words.

From the remaining tokens, the 3000 most frequent words are retained. This dictionary defines the vocabulary that the model uses when converting emails into numerical features.

Feature Extraction and Labeling

Each email is converted into a numerical feature vector based on the dictionary. The feature vector contains word counts indicating how often each dictionary word appears in the email content.

Features are extracted starting from the third line of each email, consistent with the assignment instructions. Labels are assigned automatically based on the filename, with spam emails labeled as 1 and non-spam emails labeled as 0.

The resulting feature matrices and label arrays are used as inputs for model training and testing.

Model Training

The Gaussian Naive Bayes classifier is trained using the feature matrix and labels derived from the training emails. The model learns statistical patterns in word frequencies associated with spam and non-spam messages.

Although Gaussian Naive Bayes assumes continuous features, it is used here to match the assignment’s specified approach and reference implementation.

Prediction and Evaluation

After training, the model predicts labels for the test emails. The predicted labels are compared against the true labels to evaluate performance.

Model performance is measured using classification accuracy, which represents the proportion of correctly classified test emails.

Packages Used

The notebook relies on the following Python packages:

The Python standard library for file handling and directory traversal

NumPy for numerical arrays and feature matrix storage

Pandas for data handling support

The Counter class from the collections module for counting word frequencies

scikit-learn for the Gaussian Naive Bayes classifier and accuracy evaluation

These packages support the full workflow from raw email files to model evaluation.

Running the Notebook

To run the notebook correctly, the training and test email folders must be located in the same directory as the notebook, using the original folder names provided with the assignment. The notebook should be executed sequentially from top to bottom in a Python notebook environment such as Google Colab or Jupyter Notebook.

All required packages must be available in the environment prior to execution.

Output

When the notebook is run correctly, it prints progress messages for each major stage of the workflow, followed by a final classification accuracy score that reflects the model’s performance on the test dataset.

Final Notes

This project is designed to closely follow the CA02 assignment instructions and reference notebook. The implementation reflects the intended learning objectives of the assignment and emphasizes understanding the full machine learning pipeline rather than model optimization or alternative approaches.
