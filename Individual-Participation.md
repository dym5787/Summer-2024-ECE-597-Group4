# Task Distribution

- ## **Dingyang Miao**: Data preprocessing and Feature Extraction
    ### Comparing Two Datasets (Normal Emails and Abnormal Emails):
    Extract common features shared by both datasets.
    Remove the remaining parts that are not common between the two datasets.
    
    ### Cleaning the Data Content:
    Convert text to lowercase
    Remove HTML tags
    Remove URLs
    Remove email addresses
    Remove special characters and punctuation
    Remove repeated characters
    Tokenize the text
    Remove stopwords
    Perform lemmatization
    Normalize common abbreviations
    ### Extracting Data Features:
    I utilized two different methods to extract features from spam texts: TF-IDF and Gensim's Word2Vec. The TF-IDF method assigns scores to words based on their frequency and inverse document frequency, capturing the importance of words in the dataset. The Word2Vec method, on the other hand, generates word embeddings that capture the semantic relationships between words by considering their context within a specified window.
    The features extracted are the same, but there is a difference in the order in which they are placed.

  
- ## **Li Zhang**: Random Forest
- May through June 13
I focused on setting up the random forest classifier model and constructing data preprocessing during this period. The dataset was extremely imbalanced, so I used all spam emails and resampled the regular emails to build a smaller, balanced dataset with a ratio of 1:10 for training. After cleaning and resampling the data, I use TF-IDF vectorization to convert the text for model training.

- June 20
This week, I implemented a baseline classifier using the dummy classifier to get a better overview of the initial performance as a baseline. Accuracy: 0.8428, AUC: 0.5147.
Besides, I began to use grid search cross-validation to find the best tuning parameters of the Random Forest classifier with TF-IDF.
Accuracy: 0.9661, AUC: 0.9749.

- June 27
I continue using grid search cross-validation to determine the optimal hyperparameters for the Random Forest classifier. To maximize performance metrics using AUC. After that, find the best parameters as max_depth =30, max_features = 'log2', min_samples_split = 2, n_estimators =500. Then, I used SMOTE and undersampling techniques to deal with the imbalanced dataset. 

- July 4
I experimented with Random Forest using different embeddings (Bag of Words and Word2Vec) and reran grid search cross-validation for each technique. Results:  TF-IDF: Accuracy = 0.9638, AUC = 0.9773. Bag of Words: Accuracy = 0.9760, AUC = 0.9914. Word2Vec: Accuracy = 0.9786, AUC = 0.9907.

- July 11
I continued exploring the Random Forest using different embeddings and found that the accuracy with Bag of Words and Word2Vec reached a high of 0.97. I then applied imbalanced data handling techniques and discovered that the Random Forest classifier with Bag of Words embedding and balanced features achieved the highest performance: Accuracy: 0.9849, Precision: 0.9437, Recall: 0.8862, AUC: 0.9948.
 
- ## **Jiaxing Yao**: SVM
- June 13 - 20
- I successfully completed the construction of the phishing email detection model and performed preliminary optimization and evaluation.
- First, because the dataset was extremely unbalanced, I adjusted the ratio of normal emails to phishing emails to 10:1.After that, I set class_weight to be balanced in the SVM parameter settings to further balance the ratio of normal emails to phishing emails.
- Then, text vectorization was performed by TF-IDF and the SVM model was used for training.
- Hyper-parameters were optimized by grid search and cross-validation, and hyper-parameter filtering was performed based on the recall's scores, which ultimately resulted in the best model parameters so far.
- The accuracy of the model on the training and test sets is 90.88% and 91.68%, respectively, and the precision, recall and F1 score on the test set are 52.43%, 91.89% and 66.76%, respectively.

- Entire July
- During feature extraction, I performed embedding operations and used grid search based on recall scores to find the best parameters. Ultimately, my model achieved a recall score of 96.75% and an accuracy of 96.64% on the test set. Additionally, there is a set of parameters that can achieve an accuracy of 98.08%, but the recall score is only 90.26%.

- Applied Bags of words, collected results, compared results and drafted report.


- ## **Lian Duan**: Naive Bayes
I implement a Naive Bayes classifier to address the machine learning task. The process began with data preparation, including loading the dataset, handling missing values, and encoding categorical variables. I then split the data into training and testing sets and addressed class imbalance using the SMOTE technique. For feature extraction, I use TfidfVectorizer to convert text data into numerical features and train a MultinomialNB classifier 
- I train and test the data under Naive Bayes module.
- I obtain that the accuracy after smote is 99.38%, and the percision is 71%, recall is 97%, and F1-score is 79%.
- And I trained the data with Naive Bayes modle, after training, the accuracy is 0.9975, and the macro avg recall is 0.76, while the weighted avg one is 1.00. For the F1 score, value of macro avg is 0.84, the weighted avg one is 1.00. Both of the precision are 1.00


- ## **Xiaotian Gan**: LLM - t5-base
Individual-Participation
- 06/20
- This week, I focused on enhancing a text classification model to accurately distinguish between normal and phishing emails. I fine-tuned a T5 transformer model, troubleshooting and optimizing various parameters and data preprocessing steps. My efforts included debugging code errors, refining the model's predictions to output binary results, and ensuring the accuracy of predictions through meticulous testing and adjustments.
- 6/28
- This week, we focused on refining and debugging a machine learning model using the T5 architecture in a Python environment. We addressed various challenges related to data preprocessing, model training, and the utilization of specific utilities such as Accelerate for optimized training. Issues such as input tensor dimensions, tokenizer warnings, and configuration mismatches were systematically resolved. Additionally, we worked on ensuring the model could correctly interpret and process input data to improve its training efficiency and output accuracy. Through iterative testing and adjustments, we aimed to enhance model performance and streamline the training process using advanced techniques like mixed precision training.
- 6/28
- This week, I continued to train my model using PEFT, which doubled the training speed. However, the accuracy slightly decreased from 90% to 88%. I believe the moderate accuracy is due to the cleanliness of the training set. During preprocessing, many common words such as 'the', 'to', and 'and' were removed, and the training set contained a significant amount of noise, including emails that are incomprehensible to humans. These factors suggest that the dataset may not be ideally suited for large language models. Additionally, I began drafting my report this week and plan to make further adjustments to the model and finalize the report next week. This summary encapsulates my efforts and progress over the week.


- ## **Lepeng Zhou**: Transformer encoder from the paper "Attention is all you need (2017)"
#### 06/22 & 06/23
- Researched and studied the mathematics and algorithms behind the Transformer architecture.
- Took detailed notes on the concepts and theories understood.
#### 06/25 & 06/26
- Followed the original Transformer paper and various online tutorials.
- Implemented key building blocks including:
  - Input Embedding
  - Positional Encoding
  - Multi-head Encoder
  - Normalization
  - Feedforward Network
- Implementation is complete but not yet tested.
#### Entire July
- tried different implementation of the final classifier layer
- Finished implementation and debug code
- tuning and experiment with parameter settings
- Report the best result.
