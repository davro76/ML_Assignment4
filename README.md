# ML_Assignment4
Introduction
 
- This assignment is about Regression Trees (combined with prior material too)
 
- You are going to use a modified* version of the Hitters dataset. You can find this file on Blackboard (Regression Trees folder/ Assignment 4 folder)

* This file has been cleaned to remove the rows with missing data. Also, some of the variables have been discarded. 
 
- Use the following link to read more info about the original Hitters dataset (remember we are using a modified version of the original one):
https://rdrr.io/cran/ISLR/man/Hitters.html

- The outcome variable to predict is the log of Salary, where Salary is the player’s salary in the 1987 season. Notice that the column called “Salary” in this dataset actually records the log of the Salary.

Note: Evidence suggests that better predictive models can be obtained for the log of the Salary than for the Salary. 


Question 1:

Estimate a regression tree to predict the log of the Salary (i.e., the column called Salary in this dataset).

Requirements that MUST be followed to estimate this tree:

- Use all 13 predictors when constructing the tree. Some of these predictors will be part of the final tree, and some will not, but you must include them all in principle when building the tree.
- Use the train_test_split() method and use 80% of the players to train the tree.
- Create a parameter grid that includes all the following parameters: 'max_depth', 'min_samples_split', 'min_samples_leaf', and 'min_impurity_decrease'.
- Use the GridSearchCV() method with cv=5 and scoring='neg_mean_squared_error'


1a) Report the mean squared error of the chosen tree evaluated on the test dataset you created earlier (i.e., the 20% players that you left out earlier to serve as a test dataset)

1b) Use the leftmost and the rightmost branches of your tree and write out the rules expressed by these branches. Notice that you have to write two rules (one for the leftmost branch and another one for the rightmost branch)

Hint: Why do we mean by a rule derived from a branch? For example: If X1< 10. 5 AND X4 >= 23.2 AND X9 <0.5, then the predicted value of Y is 60.5.


Question 2:

2a) Apply the abess to the whole dataset and select the best predictors to include in a multiple linear equation to predict the log of the Salary. Apply abess just to identify and report the best predictors to include, do not bother estimating the linear equation with these predictors (that will be part b)

2b) Use the train_test_split() method and use 80% of the players to obtain the equation formed by the predictors identified in part a. Report this equation (i.e., write out the equation. Example: Estimated log of salary = 10.56 + 7.7* Salary + 23.1 * Hits ….)

2c) Report the mean squared error of the equation obtained in part b evaluated on the test dataset you created in part b (i.e., the 20% players you left out earlier to serve as a test dataset). Compare the Regression Tree obtained in question 1 with this linear equation. Which one is better?

Question 3:

Apply the post-pruning methodology learned in class (i.e., the cost complexity pruning) to estimate a new regression tree with the Hitters dataset. Compare this tree with the one obtained in question 1. Which tree is better? Justify.

