# AMAZON FINE FOOD REVIEWS

# Note :
    1. Dataset is preprocessed , cleaned and time-based splitted(Train , Test , Cross-Validate).
    2. SAMPLE_SIZE: 100000 Reviews (70K-TRAIN , 15K-CROSS_VALIDATE , 15K-TEST).

# 1. k-nearest neighbour (K-NN) :
# Objectives :
    1. TO FIND THE OPTIMAL VALUE OF 'K'(No. of nearest neighbours)
    2. TO FIND THE ACCURACY SCORE OF OUR PREDICTION ON TEST DATASET.
# Final Table :    
      +-----------------+---------+-----------------+------------------+
      |    VECTORIZER   |  MODEL  | HYPER PARAMETER | AREA UNDER CURVE |
      +-----------------+---------+-----------------+------------------+
      |       BOW       |  BRUTE  |        15       |     0.71573      |
      |       BOW       | KD-TREE |        33       |     0.71964      |
      |      TFIDF      |  BRUTE  |        3        |     0.50891      |
      |      TFIDF      | KD-TREE |        45       |     0.70534      |
      |    AVG-W2VEC    |  BRUTE  |        49       |     0.87921      |
      |    AVG-W2VEC    | KD-TREE |        51       |     0.88078      |
      | TFIDF-AVG W2VEC |  BRUTE  |        3        |     0.48951      |
      | TFIDF-AVG W2VEC | KD-TREE |        37       |     0.44583      |
      +-----------------+---------+-----------------+------------------+
# Conclusions :
    1. AVG-W2VEC KD-TREE model is the best model with AUC value 0.88 .
    2. TFIDF-AVG W2VEC KD-TREE model has the lowest value of AUC(  0.44583 ) among all the models.
    
# 2. Naive-Bayes :
# Objectives :
    1. TO FIND THE OPTIMAL VALUE OF 'alpha'(Hyperparameter)
    2. TO FIND THE ACCURACY SCORE OF OUR PREDICTION ON TEST DATASET
# Final Table :
      +------------+-----------------+------------------------+------------------+
      | VECTORIZER | LENGTH-INCLUDED | HYPER PARAMETER:-alpha | AREA UNDER CURVE |
      +------------+-----------------+------------------------+------------------+
      |    BOW     |        NO       |          0.1           |     0.90523      |
      |    BOW     |       YES       |          0.1           |     0.90521      |
      |   TFIDF    |        NO       |          0.01          |     0.93186      |
      |   TFIDF    |       YES       |          0.01          |     0.91737      |
      +------------+-----------------+------------------------+------------------+
# Conclusions :
    1. TFIDF models works better than BOWs models .
    2. TFIDF model not containing review length as a feature is the best model with AUC value 0.93186.
    3. BOWs model containing review length also as a feature has the lowest value of AUC(  0.90521 ) among all the models.
    4. Naive Bayes Algorithm works better than KNN algorithm on text data .
     
# Logistic Regression :
# Objectives :
    1. TO FIND THE OPTIMAL VALUE OF ' lambda '( hyperparameter )
    2. TO FIND THE ACCURACY SCORE OF OUR PREDICTION ON TEST DATASET.
# Final Table :
      +-----------------+----------------+-----------------+------------------+
      |    VECTORIZER   | REGULARIZATION | HYPER PARAMETER | AREA UNDER CURVE |
      +-----------------+----------------+-----------------+------------------+
      |       BOW       |       L2       |        10       |     0.93848      |
      |       BOW       |       L1       |        1        |     0.93008      |
      |      TFIDF      |       L2       |       0.01      |     0.96399      |
      |      TFIDF      |       L1       |       0.1       |     0.95732      |
      |    AVG-W2VEC    |       L2       |       0.1       |     0.90063      |
      |    AVG-W2VEC    |       L1       |       0.1       |     0.90063      |
      | TFIDF-AVG W2VEC |       L2       |        10       |     0.63174      |
      | TFIDF-AVG W2VEC |       L1       |      0.001      |     0.63163      |
      +-----------------+----------------+-----------------+------------------+
# Conclusions :
    1. TFIDF vectorizer performs best among all the models with AUC values ( 0.96399 ( L2 ) , 0.95732 ( L1 ) )
    2. TFIDF-AVG W2VEC are the poorest among all the models with lowest AUC values  ( 0.63174 ( L2 ) , 0.63163 ( L1 ) )
    3. Number of elements of W* being zero( sparsity ) is 44995 in case of BOWs and 1116760 in case of TFIDFs
    4. There are 23 features in BOWs model which are collinear 
    5. In general L2 regularization performs better than L1 regularization 
    
    
    
