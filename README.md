# Handwriting Digit Recognition
A comparison of Decision Tree and Naive Bayes calssifiers in handwriting digit recognition.


## Project Overview
The purpose of this exploration is to determine the efficacy of different algorithms for use in handwriting recognition. This will be accomplished by building two separate models using decision tree induction and Naive Bayes and seeing which preforms better a better job at prediction.

## Data Set
The data originates from the Kaggle Digit Recognition competition (url: [https://www.kaggle.com/c/digit-recognizer/overview](https://www.kaggle.com/c/digit-recognizer/overview), which utilizes are dataset obtained from the MNIST.

The data was then split into training and testing sets using a 0.8 / 0.2 split.

## Classifiers

### Decision Tree
Both untuned and tuned decision trees were created to measure performance. For the tuned decision trees, both tune length and cross-verification x10 were utilized.

### Naive Bayes
The e1071 package was used to create a Naive Bayes model. In order to prevent the occurence of classes with no predictors, all columns with zero variance were removed. Both untuned and tuned Naive Bayes models were created to measure performance. For the tuned models, the best.tune() method and cross-verification x10 were utilized.

## Algorithm Comparisons

When comparing the initial, untuned versions of the Decision Tree model and the Naive Bayes model, the Decision Tree exhibited much worse performance than the Naive Bayes model. It can also be seen that, when viewing as a graphical tree, that the Decision Tree limited itself to only three levels in an effort to reduce overfitting. The Naive Bayes model, in comparison, performed better at prediction from the outset. This can be explained by comparing the algorithms themselves. 

Decision Trees utilize chains of data to determine classification. Thus, with a data set that has a large number of attributes (in the case of digit recogniztion, 785), classification becomes a much more difficult task. One can tune a package, such as caret, with attributes, such as tuneLength, to force it to create a tree that encompasses all 10 digit possiblities, but that opens up the possibility of overfitting as the tree grows and become more intricate.

Naive Bayes models, on the other hand, determine probabilities by considering all attributes to be independent from each other. Therefore, Naive Bayes algorithms are ideal for datasets where there are large numbers of attributes, or where there is a high amount of variance in the data. Without tuning, the Naive Bayes model had a much higher level of performance than the Decision Tree model.

It should be noted that the Decision Tree model precision can be brought up to be similar to Naive Bayes precision through the use of tuning. However, one runs the risk of overfitting the to the test dataset, as the decision trees become very large and convoluted. It would be better to instead tune the Naive Bayes model to achieve a higher level of peformance in order to avoid the risks that come with Decision Trees.