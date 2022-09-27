$$
\newcommand{\pr}{\text{I\kern-0.15em P}}
\newcommand{\Ha}{H_a}
\newcommand{\Ho}{H_0}
\newcommand{\pv}{\text{p-value}}
\newcommand{\ss}{\sum_{i=1}^{n}}
$$


# Notes

## Week 6
### Module 3 Week 6B

#### Multiple Linear Regression and Statistical Inference

- Recall that $$ is the variance of $\epsilon$ and therefore plays an important role in assessing the utility of the estimated regression model. 

- $\sigma^2$ is typically unknown and therefore must be estimated with $s^2$. 

- $s^2 = \frac{SSE}{n - (k + 1)} = MSE$

- $s = \sqrt{MSE}$ is the standard deviation of the error term. 

- $2s$ is a useful approximation of the range in which 95\% of all predictions for $y$ values will fall, at a given $x$ value.

    

- We want to know if the model is adequate for predicting $y$.

- We saw how to conduct a t-test for an individual parameter in the simple linear regression model. 

- It is not advisable to conduct numerous t-tests for each parameter in the multiple linear regression model to determine if the model *overall* is useful. 

    - True Type I error rate is much higher => higher probablity of incorrectly rejecting the Null => use *Joint Hypothesis Test* to assess the *overall* utility of the model

- F-test: a joint hypothesis test for testing if all slope coefficients are equal to zero.

    

- F-test (a joint hypothesis test for assessing the utility of the overall model): 

- $\Ho$: $\beta_1 = \beta_2 = ... = \beta_k = 0$

- $\Ha$: at least one $\beta \neq 0$

- The test statistic used is an F-statistic that follows an F-distribution 

- F-stat $= \frac{(\sum_i (y_i - \bar{y})^2 - \sum_i (y_i - \hat{y})^2) / k}{(\sum_i (y_i - \hat{y})^2) / (n - (k + 1))} = \frac{(SST - SSE) / k}{SSE / (n - (k + 1))} = \frac{MS_{model}}{MSE}$

    - $k$ is the numerator $df$
    - numerator: represents the variation in $y$ *explained* or accounted for by the model; the sum of squared deviations for $y$ from its mean minus the sum of errors squared, all divided by the numerator $df$; like the Mean Square of Error Between groups in the One-Way ANOVA test
    - $(n - (k + 1))$ is the denominator $df$
    - denominator: represents the *unexplained* portion of the model; the sum of errors squared devided by the denominator $df$

- Always a one-tailed (right-tailed) test 

- A helpful alternative formula for F-stat $= \frac{R^2 / k}{(1 - R^2) / (n - (k + 1)}$

    - Interpretation:
        - $R^2$ - represents linearly explained variation
        - $1 - R^2$ - represents linearly un-explained variation
        - If the ratio of explained to unexplained varation is large => the model as a whole is useful


    

- E.g. Suppose we estimate a regression model with a sample of 40 observations and 4 predictor variables. The estimated model has an R-squared $= 0.40$. 

- Joint hypothesis test for all of the model’s slope coefficients (F-test) 

- $\Ho$: $\beta_1 = \beta_2 = \beta_4 = \beta_4 = 0$

- $\Ha$: at least one $\beta \neq 0$

- F-stat $= \frac{0.40 / 4}{(1 - 0.40) / (40 - (4 + 1))} = \frac{0.10}{0.017} = 5.88$

- $df_{numerator} = 4$, $df_{denominator} = 35$

- p-value $= 0.00996$ 

- $0.00996 < 0.05$ => reject $\Ho$, at least one $\beta ≠ 0$ 

    - => The model is statistically useful; but doesn't necessarily mean "the best" model; the F-Test takes the model being correct as a given.

    

- We can also use an F-test for a joint hypothesis test for *any subset* of a model’s coefficients. 

    - Useful whether to include a set of $x$'s in the model when not sure from a theoritical/logical perspective

- Under the assumption of the error term having a constant variance (i.e. **Homoscedasticity**) we can use the following intuitive formulas for calculating an F-stat.

- Let $q$ denote the number of $\beta$'s being tested; i.e. the *number of restrictions* or coefficients that are set to $0$ under the Null => if the Null is true, those $x$-terms go away and cannot explain the variation in the outcome of interest

- F-stat $= \frac{ (R^2_{unrestricted} - R^2_{restricted}) / q}{(1 - R^2_{unrestricted}) / (n - (k + 1))}$

- F-stat $= \frac{ (SSE_{unrestricted} - SSE_{restricted}) / q}{(SSE_{unrestricted}) / (n - (k + 1))}$ (<- alternative formula)

    

- E.g. Suppose we estimated the following regression model (assume $n = 40$ ): 

- $y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_3 + \beta_4 x_4 + \beta_5 x_5 + \epsilon$

- This is the *unrestricted* model (the full model). Assume it has an R-squared equal to $0.52$. 

- Suppose we want to test if $\beta_3$, $\beta_4$, $\beta_5$ jointly equal $0$.

- $\Ho$: $\beta_3 = \beta_4 = \beta_5 = 0$

- $\Ha$: at least one $\beta \neq 0$

- Under $\Ho$, the model is *restricted* and becomes: 

- $y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \epsilon$ 

- Assume the restricted model has an R-squared equal to $0.43$. 

- F-stat $\frac{(0.52 - 0.43) / 3}{(1 - 0.52) / (40 - (5 + 1))} = \frac{0.03}{0.014} = 2.14$

- $df_{numerator} = 3, df_{denomenator} = 35$ 

- p-value $= 0.113$ 

- $0.113 > 0.05$ => fail to reject $\Ho$

    - => $x_3, x_4, x_5$ do not seem to provide a substantial amount of explanatory power beyond what is already provided by $x_1, x_2$

    

- We can also test *individual* slope coefficients in *multiple regression model* using a *T-Test*.

- Suppose we estimate the following regression model: 

- $y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_3 + \beta_4 x_4 + \beta_5 x_5 + \epsilon$

- Inferences about individual slope coefficients: t-test 

    - Can be *one-* or *two-tailed*

- For example we could test if there is a linear relationship between $y$ and $x_1$). 

    - t-stat $= \frac{\hat{\beta}_1 - \beta_{H_0}}{SE_{\hat{\beta}_1}}$
        - SE not practical to be computed by hand, but same interpretation: Standard Deviation of a Sampling Distribution (recall: Sampling Distribution (used under the assumption of Null being true) is a Probability Distribution for an estimate)

    - $df = n – (k + 1)$

- Confidence interval for $\hat{\beta}_1 = \hat{\beta}_1 \pm t_{\alpha/2} ∗ SE_{\hat{\beta}_1}$

    

- E.g. Suppose using a sample of 38 observations to estimate the model on the previous slide produces: 

- $\hat{y} = 3.1 + 2.7 x_1 − 6.2 x_2 + 0.4 x_3 + 5.8 x_4 − 2.9 x_5$

- t-test for $\beta_1$: 

- $\Ho$: $\beta_1 = 0$

- $\Ha$: $\beta_1 \neq 0$

- Assume $SE(\hat{\beta}_1) = 1.02 $

- t-stat $= \frac{2.7 - 0}{1.02} = 2.65$ 

- $df = 38 − (5 + 1) = 32$ 

- p-value $= 0.012$

- $0.012 < 0.05$ => reject $\Ho$, there is a linear relationship between $y$ and $x_1$

    - If failing to reject the $\Ho$ => either: no relationship between $y$ and $x_1$ OR a linear relationship exists but we made a Type II error OR a relationship exists but it is *not* linear.

- 95\% confidence interval for $\hat{\beta}_1 = 2.7 \pm 2.04 ∗ 1.02 = (0.62, 4.78)$

    

- Multiple coefficient of determination ( $R^2$ ) 

    - Calculated like $R^2$  for the simple linear regression model 
    - $R^2 = 1 − \frac{SSE}{SST}$ 
    - Interpretation remains the same: fraction of *sample* variation in $y$ that is linearly explained by the model.
        - Closer to 1 => better fit 
        - Clower to 0 => worse fit
        - Equalt to 1 if sample number of parameters as observations => a useful statistic only when the number of observations is much larger than the number of parameters to estimate
        - Because Least Squares miminizes $SSE$, it maximizes $R^2$

- $R^2$ - is a sample statistic => good fit in the *sample* does not necessarily mean the model provides a good fit to the observations in the entire *population*.

- $R^2$ will *always* increase if an additional predictor is added to the model, even if it makes no sense to include that predictor. For this reason, a preferred measure of fit for a multiple regression model is ”adjusted $R^2$” . 

- Adjusted-$R^2$ adjusts $R^2$ to account for the (large) number of predictors and (small) sample size. 

- $R^2_A = 1 − \frac{n - 1}{n - (k + 1)} (1 - R^2)$

- $R^2_A < R^2$



