Introduction and Summary

In this work I will evaluate and rank a number of ML models to analyze and predict the disease given
some health markers in patients. The work includes data visualization to establish correlation of
features to outcome and also determine if data has outiers or any other problems that require special
treatment. 

Main Product

The main outcome of this work would be a ML model that could be used to do early prediction of disease
on patients given some health markers and medical history.

Main Findings

1.-Some of the features like Glucose, Skin thickness and BMI bear high correlation with postive outcome.

2.-Some data impurities were found and eliminated thanks to visualization of the data.

3.-Recall was selected as our main metric as it enables us to measure how many of the postives our 
models manage to capture, please see more detail on the use of this metric in the document.

4.-Varios models were initially evaluated in the dimension of a single hyper-parameters to get an idea
of their baseline recall. Further refinement will be doen at a later time with GridSearchCV

5.-A table of the initial performance of all the ML algorithms used is presented sorted by recall, 
showing our top ML classifier would be SVC.

6.-The problem was found to be a binary classification problem as the outcome has two possible values:
negative(0) or positive(1).

7.-The ML classifiers studied include: Decision Trees, SVC, Gradient Boos Classifier, Random Forest Classifier,
Logistic Regression, KNN Classifier, MLP Classifier.

8.-Other tools like Confusion Matrix and ROC AUC were instrumented to be used to display results later

Future work

1.-A section using GridSearchCV will be added to explore a wider hyperparamter space.

2.-Polynomial preporcessing may be added to see if that improves our metric.

3.-Feature selection will be applied when we use the polynomial transformation to keep processing in check.


