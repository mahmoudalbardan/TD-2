# TD-2


The challenge
-------------

In this exercise we'll implement logistic regression and apply it to a classification task. We'll also improve the robustness of our implementation by adding regularization to the training algorithm. and testing it on a more difficult problem.

Logistic regression
In the first part of this exercise, we'll build a logistic regression model to predict whether a student gets admitted to a university. Suppose that you are the administrator of a university department and you want to determine each applicant's chance of admission based on their results on two exams. You have historical data from previous applicants that you can use as a training set for logistic regression. For each training example, you have the applicant's scores on two exams and the admissions decision. To accomplish this, we're going to build a classification model that estimates the probability of admission based on the exam scores.


- Load the data, examin it using pandas methods 
- Scatter plot of the two scores and use color coding to visualize if the example is positive (admitted) or negative (not admitted).
- Implement the sigmoid function and test it (by plotting it ) using generated data
- Write the cost function that takes (X,y,theta) as entries
- Extract your dataset (to be used in ML) and labels from the dataframe and name them (X, y).
- Initialize your parameter vector theta as a zero np.array of size 3 
- Compute the initial cost (with initial values of theta) 
- Copy the function below in your code. It computes the gradient during the optimization process
```
def gradient(theta, X, y):
    theta = np.matrix(theta)
    X = np.matrix(X)
    y = np.matrix(y)
    parameters = int(theta.ravel().shape[1])
    grad = np.zeros(parameters)
    error = sigmoid(X * theta.T) - y
    for i in range(parameters):
        term = np.multiply(error, X[:,i])
        grad[i] = np.sum(term) / len(X)
    return grad
```
 - Call the function gradient with the initial values of `theta`
 - Use the function `fmin_tnc` from `scipy.optimize` to find the optimal parameters `theta_opt`
 - Write a prediction function that takes an input vector `**x**` and outputs its class `y`
 - Write a function that estimate the accuracy of your model by a Kfold cross validation
 - Compute the confusion matrix of your model
 - Use the built in function `sklearn.linear_model.LogisticRegression` and estimate the accuracy of your model using LOOCV (leave one out cross validation)


https://members.loria.fr/FSur/enseignement/apprauto/
