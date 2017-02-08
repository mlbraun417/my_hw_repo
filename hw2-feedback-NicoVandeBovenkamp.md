### ***Project 2 Feedback***

***Nico Van de Bovenkamp***
***

**Overall** Good work! All of your answers are precise and concise. And you made very good use of many libraries we have seen thus far. Try out those bonus questions!

**Some Notes**

* **Q.10** Good work trying out some statistical tests here! However, I think the null-hypothesis was switched here. The null-hypothesis according to the [documentation](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.normaltest.html) is that a sample comes from a normal distribution. Thus, if a p-value is smaller, then it is actually *more unlikely* that the data comes from a normal distribution. Thus, when you did the log-transformation, it actually became slightly more skewed.
