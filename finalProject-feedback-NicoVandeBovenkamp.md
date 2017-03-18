### ***Final Project - Exploratory Analysis Feedback***

***Nico Van de Bovenkamp***
***

**Overall:** This notebook is a great start to working with your dataset, cleaning some stuff up, and gaining some insight! Great work on imputing the medians of the data!

**Analysis going forward:** Your data seems pretty set up and prepped (unless you would like to still append some of that outside data!). Now, you are ready to split your data into train and test, potentially scale everything, and build out your model! I would suggest starting out with Statsmodels API to maybe get some insight into the statistical significant of each feature cleanly. Then I would move on to SKLearn and use the some cross-validation to tune a solid model. Finally, try out some non-linear models (random forrest), but watch out for over-fitting!

**Some Notes and Thoughts:**

* **Scaling Data:** Check out the [Standard Scaler](http://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html) package. The Standard Scaler will scale all numerical data, which will allow for some easier computation and more efficient computation. This part can actually be quite critical for distance based functions and SVMs. Additionally, you will be able to see the data distributions much more clearly (though other transforms could accomplish this just as well)!
* **Model Tuning:** Always remember your Train/Test Split, Regularization, Cross-Validation, Visualizing learning paths, etc.
* **Plotting and Evaluation:** In your case, you will be using some regression model to find the impression rate. Thus, you should model via Mean Squared Error (or Log-Likelihood), and then you can plot in many ways! You can plot residuals (very key), KDE (distributions) of the actual Rate and Predicted Rate, and you can even compute expected values if you have the associated cost of advertising for a certain amount of time, device, size, etc.!
* **Feature Importance:** One nice feature of random forests, is the ability to use, and then plot, the `.feature_importance_` of each feature (usually calculated via lowest entropy or gini coeffient). In These types of *why and what factors influence [blank]* problems, the prediction power of a feature can be very handy!


***A Table of Key Evaluation Metrics and Visuals:***

*Throwing this in here too! Below is a brief set of many ways you can communicate/measure results that will be useful for your final project. Please let me know if you have any questions!*

| Metrics | |
|--- | --- |
| *Classification* | Accuracy, Precision, Recall, AUC Score, Lift, F-Score, Log-Loss, Gini, Entropy/Information Gain, Statistical Significance (p-value) |
| *Regression* | Mean Squared Error, Mean Absolute Error, Log-Likelihood Estimation, Statistical Significance (p-value) |

| Visualizations | |
|--- | --- |
| *Model Tuning* | Learning Curves, Regularization Learning Paths with an Error Metric, Model Error stepwise increasing feature set size |
| *Classification* | ROC Curve, Feature Importance Charts, Lift Curves, Expected Value Plots |
| *Regression* | Residual plots(!), KDE and KDE of Predicted Values, Expected Value |
