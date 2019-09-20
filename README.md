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


