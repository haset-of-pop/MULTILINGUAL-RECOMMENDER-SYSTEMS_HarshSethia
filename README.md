# MULTILINGUAL-RECOMMENDER-SYSTEMS_HarshSethia
It consists of two main components:  User sessions: List of products that a user has engaged with in chronological order Product attributes. Various details like product title, price in local currency, brand, color, and description.
This repository contains code and data for building a recommendation model using a transformer-based architecture for multiple locales. The model utilizes word embeddings generated from language models trained on different locales to improve the quality of recommendations. The process of prediction involves several steps, as described below:

TEST and TRAIN Datasets at - https://www.aicrowd.com/challenges/amazon-kdd-cup-23-multilingual-recommendation-challenge/problems/task-1-next-product-recommendation/dataset_files


# Data Preprocessing and Word Embedding Training
The preprocessed training data is loaded from the "products_train_processed.csv" file.
The data is filtered to include only the records for a specific locale, such as the UK.
The text data (brand and title) is combined to create a new "text" column.
Missing values in the "text" column are removed.
The text data is tokenized into individual words.
Word2Vec models are trained on the tokenized text data to generate word embeddings.
Optionally, a phrase model can be trained to capture common phrases in the text data.
# Building the Recommendation Model
The training data is loaded, consisting of the "products_train_processed.csv" and "sessions_train.csv" files.
The data is filtered to include only the records for a specific locale, such as the UK.
The sessions and products data are merged based on the "next_item" column.
The required columns, "prev_items" and "next_item", are selected from the merged data.
The "prev_items" column, which contains sets of product IDs the user interacted with, is split into individual product IDs.
The input features (prev_items) and target labels (next_item) are extracted from the filtered data.
# Training the Recommendation Model
A transformer-based model is built using the TensorFlow library.
The model architecture includes an input layer, embedding layer, transformer layer, and output layer.
The model is compiled with the Adam optimizer and sparse categorical cross-entropy loss function.
The input features and target labels are converted to tensors.
The model is trained for a specified number of epochs using the training data.
# Testing the Recommendation Model
The test data is loaded from the "sessions_test_task1_phase1.csv" file.
The data is filtered to include only the records for a specific locale, such as the UK.
The "prev_items" column is split into individual product IDs.
The input features are converted to a tensor.
Predictions are generated using the trained recommendation model.
The top 100 recommended product IDs for each session are extracted from the predictions.
# Evaluation and Conclusion
Ground truth data is prepared for each locale.
Accuracy metrics such as precision, recall, and F1 score are calculated by comparing the recommended product IDs with the ground truth.
The accuracy metrics are analyzed and plotted using line graphs.
A conclusion is drawn based on the quantitative results, highlighting the performance of the recommendation models for each locale.
The conclusion emphasizes the impact of knowledge transfer from the UK locale to improve the recommendations for non-UK locales.
Suggestions are provided for further experimentation and refinement of the models to enhance recommendation accuracy for specific locales.
By following the above process, a recommendation model is built and evaluated for multiple locales using word embeddings and a transformer-based architecture. The model leverages the knowledge gained from training on the UK locale to improve recommendations for other locales. The code and data in this repository can be utilized to reproduce the results and explore enhancements to the recommendation system for different locales.
