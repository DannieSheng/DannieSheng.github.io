# Data Science
* [Basic Data Science](#basic-data-science)
* [Statistics](#statistics)
* [Data Analysis](#data-analysis)
* [Machine Learning](#machine-learning)
* [Deep Learning]()

## Basic Data Science
### What is Selection Bias?


### What is bias-variance trade-off?
  
  **Bias**: 
- Due to oversimplification of the machine learning algorithm
- Lead to under-fitting
- Low bias machine learning algorithms
    * Decision Trees 
    * k-NN 
    * SVM
- High bias machine learning algorithms
    * Linear regression
    * Logistic regression
  **Variance**:
   - Due to complex machine learning algorithm
   - Model learns noise from the training data set
   - Lead to high sensitivity and over-fitting
   
 
* Confusion matrix
  - Basic measures derived from the confusion matrix
    * Error rate = (FP+FN)/(P+N)
    * Accuracy = (TP+TN)/(P+N)
    * Recall or Sensitivity (TPR) = TP/P
      Of all true positives, how many of them are predicted to be positive correctly
    * Precision (Positive predicted value) = TP/(TP+FP)
      Of all predicted positives, how many of them are actual positive
    * Specificity (TNR) = TN/N
    * F-Score (harmonic mean of precision and recall)
     = 2(Precision*Recall)/(Precision+Recall)
    * ROC curve: a graphical representation of the contrast between true positive rates and false-positive rates at various thresholds.
    It shows the trade-off between TPR and FPR (Sensitivity and FPR)
      

## Statistics
* Normal distribution

* Correlation and covariance ([details explained](https://www.mygreatlearning.com/blog/covariance-vs-correlation/#covariance))
  
  **Correlation**: Quantitatively measures how strongly two variables are relates
  **Covariance**: Measures the extent to which two random variables change in cycle
  

* Point Estimates vs. Confidence Interval
  
  **Point Estimation**: gives us a particular value as an estimate of a population parameter. 
  Method of Moments and Maximum Likelihood estimator methods are used to derive Point Estimators for population parameters.
  
  **Confidence interval**: gives us a range of values which is likely to contain the population parameter. 
  The confidence interval is generally preferred, as it tells us how likely this interval is to contain the population parameter. 
  This likeliness or probability is called Confidence Level or Confidence coefficient and represented by 1 — alpha, where alpha is the level of significance.
  

* What is the goal of A/B Testing?

    A/B Testing is a hypothesis testing for a randomized experiment with two variables A and B.
  The goal of A/B Testing is to identify any changes to the web page to maximize or increase the outcome of interest. 
  A/B testing is a fantastic method for figuring out the best online promotional and marketing strategies for your business. 
  It can be used to test everything from website copy to sales emails to search ads.
  An example of this could be identifying the click-through rate for a banner ad.
  
* What is p-value?


* What Are Confounding Variables? 
  
    A confounder is a variable that influences both the dependent variable and independent variable.


* What Are the types of biases that can occur during sampling?
  - Selection bias: 
    the sample obtained is not representative of the population intended to be analysed.
  - Under converge bias
  - Survivorship bias
    
* Why we generally use Softmax non-linearity function as last operation in-network?

    Softmax non-linearity function takes in a vector of real numbers and returns a probability distribution.
    The output is a probability distribution: each element is non-negative, and the sum over all components is 1.

## Data Analysis
* What is Cluster Sampling?
  Cluster sampling is a technique used when it becomes difficult to study the target population spread across a wide area and simple random sampling cannot be applied. 
  Cluster Sampling is a probability sample where each sampling unit is a collection or cluster of elements.
  
* What is Systematic Sampling?
  Systematic sampling is a statistical technique where elements are selected from an ordered sampling frame. 
  In systematic sampling, the list is progressed circularly so once you reach the end of the list, it is progressed from the top again. 
  The best example of systematic sampling is equal probability method.
  
* What are Eigenvectors and Eigenvalues?
  
  **Eigenvectors** are used for understanding linear transformations. 
  In data analysis, we usually calculate the eigenvectors for a correlation or covariance matrix. 
  Eigenvectors are the directions along which a particular linear transformation acts by flipping, compressing or stretching.
  
  **Eigenvalue** can be referred to as the strength of the transformation in the direction of eigenvector, or the factor by which the compression occurs.

* Explain false positives and false negatives
  - **False positives**: wrongly classified non-events as events, a.k.a Type I error.
  - **False negatives**: wrongly classified events as non-events, a.k.a Type II error.

* Examples where a false positive is important than a false negative

* Examples where a false negative important than a false positive

* Examples where both false positive and false negatives are equally important

## Machine Learning
### How will you define the number of clusters in a clustering algorithm?
  *Within Sum of Squares*: explain the homogeneity within a cluster
  *Elbow Curve*: Plot WSS for a range of number of clusters
  
### Ensemble Learning
Ensemble Learning is basically combining a diverse set of learners (Individual models) together to improvise on the stability and predictive power of the model.
  - Bagging: implement similar learners on small sample populations and then takes a mean of all the predictions
  - Boosting: an iterative technique which adjusts the weight of an observation based on the last classification
    If an observation was classified incorrectly, it tries to increase the weight of this observation and vice versa.
    Boosting in general decreases the bias error and builds strong predictive models. 
    However, they may over fit on the training data.
    
### Parametric vs Nonparametric Machine Learning Algorithms
  - Parametric: A learning model that summarizes data with a set of parameters of fixed size (independent of the number of training examples) is called a parametric model.
    No matter how much data you throw at a parametric model, it won't change its mind about how many parameters it needs.
  - Nonparametric: A model where the number of parameters is not determined prior to training. 
    Algorithms that do not make strong assumptions about the form of the mapping function are called nonparametric machine learning algorithms. 
    By not making assumptions, they are free to learn any functional form from the training data.
    Nonparametric does not mean that they have no parameters. 
    On the contrary, nonparametric models (can) become more and more complex with an increasing amount of data.
    
## Deep Learning