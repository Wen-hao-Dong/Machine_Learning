# Python@Machine Learning, First Edition. Wei-Meng Lee

## Chapter 6 Supervised Learning--Linear Regression

Besides simple linear regression, in which we discuss relationship between one independent variable and one dependent variable, other linear relationships include:
- **Multiple Regression** Linear relationships between two or more indenpendent variables and one dependent variable
- **Polynomial Regression** Relationships between one independent variable and one dependent variable using an nth degree polynomial function
- **Polynomial Multiple Regression** Relationships between two or more indenpendent variables and one dependent variable using an nth degree polynomial function

## Chapter 7 Supervised Learning--Classification Using Logistic Regression

Unlike linear regression, **logistic regression** does not try to predict the value of numeric variable given a set of inputs. Instead, the output of logistic regression is the probability of a given input point belonging to a specific class. The output of logistic regression always lies in [0,1]

Odds are defined as the ratio of the probability of success to the probability of failure: P/(1-P). When you apply the natural logarithm function to the odds, you get the **logit function**. The logit function is the lograithm of the odds: L=ln(P/(1-P)). The logit function transfers a variable on (0,1) into a new variable on (-oo,oo). **Sigmoid function** is the reverse of the logit function, which is used to transform values on (-oo,oo) into numbers on (0,1): P=1/(1+e^(-L)).

        
        
  TN    |   FN
  
======    This set of numbers is known as the **confusion matrix**   

FP    |   TP
      
       
  **True Positive (TP)** The model correctly predicts the outcome as positive
  **True Negative (TN)** The model correctly predicts the outcome as negative
  **False Positive (FP)** The model incorrectly predicts the outcome as positive, but the actual result in negative
  **False Negative (FN)** The model incorrectly predicts the outcome as negative, but the actual result is positive
  
  Based on the confusion matrix, we can calculate the following metrics:
  
- **Accuracy** This is defined as the sum of all correct predictions divided by the total number of predictions: (TP+TN)/(TP+TN+FP+FN). Accuracy works best with evenly distributed data points, but it works really badly for a skewed dataset
- **Precision** This is defined as TP/(TP+FP). This metric is concered with number of correct positive predictions.
- **Recall (aka. True Positive Rate (TPR))** This metric is defined to be TP/(TP+FN). This metric is concerned with the number of correctly predicted positive events. 
- **F1 score** This metric is defined to be 2*(precision x recall) /(precision + recall). This is known as the harmonic mean of precision and recall, and it is a good way to summarize the evaluation od the algorithm in a single number.
- **False Postive Rate (FPR)** This metric is defined as FP/(FP+TN). FPR corresponds to the proportion of negative data points that are mistakenly considered as positive, with repective to all negative data points. In other words, the higher FPR, the more negative data points you will misclassify.

## Chapter 8 Supervised Learning-Classification Using Support Vector Machines
**Support Vector Machines (SVM)** is a classification algorithm, the main idea of which is to draw a line between two or more classes in the best possible manner. Once the line is drawn to separate the classses, we can then use it to predict future data.

**Kernel trick** is a technique in machine learning that transforms data into a higher dimension space so that, after transformation, it has a clear dividing margin between classes of data.

**Kernels** are functions that transform the data from nonlinear spaces to linear ones.

**Penealty parameter of the error term (C)** controls the tradeoff between the smooth decision boundary and classifying the training points correctly. If the value of C is high, then SVM algorithm will seek to ensure that all points are classifed correctly. The downside to this is that it may result in a narrower margin. In short, a low C makes the decision surface smooth while trying to classfy most points, while a high C tries to classify all of the points correctly.

**Gamma** defines how far the influence of a single training example reaches. A low gamma indicates that every points has a far reach while a high gamma means that the points closet to the decision boundary have a close reach. Thge higher the gamma value, the more it will try to fit the training dataset exactly, resulting in overfitting.

Some commonly used **nonlinear kernels** includes:
- Radial Basis function (RBF), aka *Gaussian Kernal*
- Polynomial kernel, a polynomial kernel of degree 1 is similar to that of the linear kernel. Higher-degree polynomial kernels afford a more flexible decision boundary.

## Chapter 9 Supervised Learning-Classification Using K-Nearest Neighbors (KNN)
**K-Nearest Neighbors (KNN)** is a relativelt simple algorithm. It works by comparing the query instance's distance to the other training samples and selecting the K-nearest neighbors. It then takes the majority of these K-neighbor classes to be the prediction of the query instance.

The number of the K will lead to *overfitting, underfitting, or generally good fit*. Overfitting, the model tries hard to fit all of the data perfectly, the problem with an overfitted model is that it will not work well with new, unseen data. Underfitting, on the other hand, occurs wehn a machine learning model cannot accurately capture the underlying trend of the data. Specifically, the model does not fir the data well enough. For KNN, ususally, setting K to a higher value tends to make your prediction more robust against noise in your data. As K increases, the boundary becomes smoother. But meanwhile, more points will be classified incorrectly. When K increases to a large value, underfitting occurs. **The key issue with KNN is then how to find out the ideal value of K to use?** We can use Cross-Validation and Parameter-Tuning K to see how they perform with the given dataset.

For KNN, there are three rules:
- The value of K cannot exceed the numbers of rows for training
- The value of K should be an odd number (avoid situations where there is a tie between the classes) for a two-class problem
- The value of K must not be a multiple of the number of classes (avoid ties)
