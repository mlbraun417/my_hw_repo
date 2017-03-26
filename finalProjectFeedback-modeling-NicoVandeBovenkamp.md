### ***Final Project - Modeling Feedback***

***Nico Van de Bovenkamp***
***

**Overall** Thank you so much for your thorough write up and draft! I really appreciated getting a clean write up, as well as the raw Notebook. You have a very good dataset for a real dataset, which is so, so cool! Did you have any further luck in appending any outside demographic data? I imagine that would make a big difference. If you have the time, I highly recommend it! In particular, your models are currently fairly limited due to the impact of population on your model, so gaining that demographic information could help balance out your model a ton. There is more going on in this scenario than just big city/small city.

**Some Thoughts**
* *Data Transforms:* Nice work on your data transformations to unskew the data! However, if you add a bit of bias into your model, that's totally fine. When you perform your log transform, it's actually good practice to just add 1 and then take the log so that you avoid the case when you apply `log(0)`. Thus, you can just perform: `log_data = np.log(feature+1)`. If you remove the zeros, you are swinging your data a good bit.
* *Model Evaluation and Error:* When evaluating how well your model preformed, you usually choose a metric to train your model and then you take another measure (often with the same metric, but it doesn't have to be) to evaluate your model on the test set. The 'Test set' is there for exactly that, testing out your model's performance. So, when you are evaluating the MSE, you actually want:

```python
lm = linear_model.LinearRegression().fit(X_train, y_train)
print "~~~ OLS ~~~"
print 'OLS MSE: ', metrics.mean_squared_error(y_test, lm.predict(X_test))
print 'OLS R2:', lm.score(X_train, y_train)

lm = linear_model.Lasso().fit(X_train, y_train)
print "~~~ Lasso ~~~"
print 'Lasso MSE: ', metrics.mean_squared_error(y_test, lm.predict(X_test))
print 'Lasso R2:', lm.score(X_train, y_train)

lm = linear_model.Ridge().fit(X_train, y_train)
print "~~~ Ridge ~~~"
print 'Ridge MSE: ', metrics.mean_squared_error(y_test, lm.predict(X_test))
print 'Ridge R2:', lm.score(X_train, y_train)
```

* *Random Forest:* Nice work with the modeling, but typically a random forest 'out of the box' is going to over-fit a bit. I highly recommend you add in some hyper-parameters and perform a Grid Search (with the cross validation) and then evaluate that fit: min-leaf-size or min-split-size, tree depth, and add more estimators (you can probably add like another hundred)!
* *Plotting Results:* When you are plotting your model results, the linear fit of the predictions against circulation are quite nice, but there are many other ways to show that. One great one is to plot a KDE and then plot a KDE of your *predicted* book circulation. Also, recall that you can always plot residuals and the MSE over various parameters/features to show how your model is (and is not) learning the data.
