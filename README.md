# Disaster_Tweets
Project using a Kaggle Competition dataset for Natural Lanuguage Processing (NLP) for predicting which tweets are disaster-related (https://www.kaggle.com/competitions/nlp-getting-started/overview). Multiple NLP models are used and compared to each other in terms of their classification performance. This dataset is a binary classification task.

# This project uses:
* TensorFlow 2.X to create, train and evaluate the performance of multiple NLP models [LSTM, GRU-cells, Bi-directional RNN, Conv1D, Transfer Learning, Ensemble model]
* Combination of Functional API and Sequential API to build the models
* Downloading and using a Kaggle dataset
* Text Vectorisation (Tokenisation) and Embedding methods (Embedding Projector Tool)

![image](https://github.com/DavAll22/Disaster_Tweets/assets/124359152/d64ec2e3-e556-40d2-97c9-2e3ea360e588)


The dataset contains ~10k text-based Tweets split into 7613 training samples and 3263 test samples (70:30). The dataset is imported as a .csv file and includes the Tweet text, location, keyword and binary label of whether the Tweet is a disaster or not.
The training dataset is further divided into a validation dataset for model training to prevent data leakage. 10% of the training data was used as validation. Validation occurs simultaneously when training the model.

For this project, 9 different models are created to evaluate which approach gives the best results:

0. Baseline model - TF-IDF score with Multinomial Naive Bayes
1. Simple Dense model
2. LSTM model
3. GRU cell model
4. Bi-Directional RNN with LSTM model
5. Conv1D model
6. Transfer Learning with pre-trained embedding layer (Universal Sentence Encoder)
7. Same as model 6 but using 10% of the training dataset
8. Ensemble model (using model 0, 2, 6) with averaging combination


# Evaluation

![image](https://github.com/DavAll22/Disaster_Tweets/assets/124359152/6010da38-4a61-4468-90a7-8c35f9c664e8)

The model using transfer learning with the USE performed the best, however comes at a cost of the speed to make the prediction being a lot higher (10x longer compared to the Baseline prediction for 3% improvement). Additionally, the other models created are very simple and can be made deeper to give better results.

![image](https://github.com/DavAll22/Disaster_Tweets/assets/124359152/b5a2dc74-fc6c-4481-95f9-c90fbf7ffdbc)

Evaluating the most wrong samples from the best performing model (model 6), its evident the wrong label was applied to the text (false negatives) and so would likely give better model results if labelled correctly.

# Predictions
The dataset does not contain labels for the test dataset, so no further analysis can be made other than inspecting the prediction results. 
