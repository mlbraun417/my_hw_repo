### ***Project 3 Feedback***

***Nico Van de Bovenkamp***
***

**Overall:** Good work on this homework! You made great use of several packages, and exhibit that you have a solid understanding of what odd rations and how logistic regression works. Also, good work utilizing/navigating pandas when you are remaking/shaping the dataframes (and other data structures)!

**A note on modeling:**
At times, model evaluation and evaluation metrics can get a bit lost because we spend a lot of time just understanding what these models are and how to run them. Think about what metrics you could use to measure how well your model learned the data! ROC Curves and AUC scores are very, very handy for classifiers. And try out some different models, hyper-parameters (regularization), cross validation, and loss-functions.

***Minor point on hand calculations of the odds ratios:***

Odds rations should be calculated as: $\beta = \frac{p}{1-p}$


Note, $p$ = $P(Prestige_1 = 1| Admit = 1)$ and $1-p$ = $P(Prestige_1 = 0| Admit = 1)$. Now, we recommend that you use these frequency tables to hand calculate the odds ratios as these probabilities are messy to calculate. Thus, we end up calculating $\beta = \frac{Odds Admitted, Prestige_1}{Odds Not Admitted, Prestige_1}$. For Prestige 1 in *Q.3* $\beta = \frac{\frac{33}{28}}{\frac{94}{245}} = 3.0718$

***In the end***, hand calculating these odds rations is not as important than really just knowing $\log(\beta) = \log(\frac{p}{1-p})$ is the coefficient of the logistic regression...
