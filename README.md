# **Credit Card Fraud Detection**

In this project, I build mutliple models to identify fraud credit card transaction trained using the dataset by machine learning group at Université Libre de Bruxelles and Worldline (https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud). 

For more references, see below.

The dataset contains information about more than 280,000 transactions by European cardholders. It containes only 492 transactions that are identified as fraud. Due to this higly imbalanced data (~0.17% fraud to genuine transaction), metrics like accuracy are not good measures of reliability of the model. The suggested metric and the one that we use to compare our models is the Area Under the Precision-Recall Curve (AUPRC).

## Target Variable
The column 'Class' indicates whether the transaction is a fraud(1) or not(0).

## Features
Most of the features (V1-V28) are a result of a Principal Component Analysis (PCA). The original features are not provided due to confidentiality issues. We  drop the 'Time' column since it represents the time elapsed between different transactions and is unlikely to be factor in whether a transaction if fraud or not since each row is an independent transaction. 

## Model Building and Evaluation Metrics
We built several classifications models and compare them.

### Decision Tree
Precision = 0.76, Recall = 0.73, f1-score = 0.75

### Random Forest: 
AUPRC = 0.82, Precision = 0.91, Recall = 0.73, f1-score = 0.81

### XGBoost:
AUPRC = 0.84, Precision = 0.88, Recall = 0.80, f1-score = 0.83

### Neural Network (20 --> 10 --> 5 --> 1):
We built a Neural Network using TensorFlow and Keras libraries with an architecture of 20 --> 10 --> 5 --> 1 layers in the neural network. The final neuron has a sigmoid activation which predicts the probability of a transaction to be fraud or not. The model is trained using the 'binary_crossentropy' loss function and the 'adam' optimizer.
AUPRC = 0.80, Precision = 0.87, Recall = 0.75, f1-score = 0.80


## References
1. Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015

2. Dal Pozzolo, Andrea; Caelen, Olivier; Le Borgne, Yann-Ael; Waterschoot, Serge; Bontempi, Gianluca. Learned lessons in credit card fraud detection from a practitioner perspective, Expert systems with applications,41,10,4915-4928,2014, Pergamon

3. Dal Pozzolo, Andrea; Boracchi, Giacomo; Caelen, Olivier; Alippi, Cesare; Bontempi, Gianluca. Credit card fraud detection: a realistic modeling and a novel learning strategy, IEEE transactions on neural networks and learning systems,29,8,3784-3797,2018,IEEE

4. Dal Pozzolo, Andrea Adaptive Machine learning for credit card fraud detection ULB MLG PhD thesis (supervised by G. Bontempi)

5. Carcillo, Fabrizio; Dal Pozzolo, Andrea; Le Borgne, Yann-Aël; Caelen, Olivier; Mazzer, Yannis; Bontempi, Gianluca. Scarff: a scalable framework for streaming credit card fraud detection with Spark, Information fusion,41, 182-194,2018,Elsevier

6. Carcillo, Fabrizio; Le Borgne, Yann-Aël; Caelen, Olivier; Bontempi, Gianluca. Streaming active learning strategies for real-life credit card fraud detection: assessment and visualization, International Journal of Data Science and Analytics, 5,4,285-300,2018,Springer International Publishing

7. Bertrand Lebichot, Yann-Aël Le Borgne, Liyun He, Frederic Oblé, Gianluca Bontempi Deep-Learning Domain Adaptation Techniques for Credit Cards Fraud Detection, INNSBDDL 2019: Recent Advances in Big Data and Deep Learning, pp 78-88, 2019

8. Fabrizio Carcillo, Yann-Aël Le Borgne, Olivier Caelen, Frederic Oblé, Gianluca Bontempi Combining Unsupervised and Supervised Learning in Credit Card Fraud Detection Information Sciences, 2019

9. Yann-Aël Le Borgne, Gianluca Bontempi Reproducible machine Learning for Credit Card Fraud Detection - Practical Handbook

10. Bertrand Lebichot, Gianmarco Paldino, Wissam Siblini, Liyun He, Frederic Oblé, Gianluca Bontempi Incremental learning strategies for credit cards fraud detection, IInternational Journal of Data Science and Analytics



