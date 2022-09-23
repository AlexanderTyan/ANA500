$$
\newcommand{\pr}{\text{I\kern-0.15em P}}
\newcommand{\Ha}{H_a}
\newcommand{\Ho}{H_0}
\newcommand{\pv}{\text{p-value}}
\newcommand{\ss}{\sum_{i=1}^{n}}
$$


# Notes

## Week 5
### Module 3 Week 5C
#### Simple Linear Regression and Statistical Inference

- The values of the calculated statistics (i.e. the $\hat{\beta}$'s) will vary from sample to sample, they are random variables. 

- How confident are we that the estimates are close to the population parameters of interest (i.e. the $\beta$)? 

- This requires statistical inference 

    - Hypothesis testing 
    - Confidence intervals

    

- Model assumptions:

    - $\mathbb{E}(\epsilon)= 0$
        - This implies that $\mathbb{E}(y) = \beta_0 + \beta_1 x$ 
    - $Var(\epsilon) = \text{constant} = \sigma^2$
    - $\epsilon \sim N(0, \sigma^2)$
    - $\epsilon$  associated with any two observations are unrelated (independent) 

- These assumptions allow us to conduct statistical inference for the parameters of interest.

    

    ![Screenshot from 2022-09-21 10-21-32](/home/tyansg/Repos/ANA500/Week 5/objects/Screenshot from 2022-09-21 10-21-32.png)



- $\sigma^2$ is the variance of the distribution of the error term. It is reasonable that the larger $\sigma^2$ is the less reliable our estimates are. 

- $\sigma^2$ plays a critical role in statistical inference. 

- $\sigma^2$ is a population parameter, it is unobserved.

- $\sigma^2$ must be estimated with $s^2$ (known as the mean squared error). 

- $s^2 = \frac{SSE}{df}$

- $SSE = \sum (y_i - \hat{y}_{i})^2$ 

- $df = n − (\text{number of } \beta \text{'s})$ 

- For straight-line (first-order) model: $s^2 = \frac{SSE}{n - 2} = MSE$

- $s = \sqrt{MSE} =$ estimated standard error of the regression model 

    

- Recall that for a normally distributed random variable, approximately 95\% of all values fall within 2 standard deviations of the mean. 

    - The least squares line gives the *mean* value of $y$ for a given $x$.
        - We should expect about 95\% of all $y$ values to lie within $2s$ of the estimated line. 

- How big does $s$ need to be to cause concerns about the reliability of the estimates? 

    - It’s a relative question 
        - The coefficient of variation (CV) can help 
        - $CV = 100 ∗ \frac{s}{\bar{y}}$ 
        - Rule of thumb: we want $CV$ to be 10% or less

    

- $y = \beta_0 + \beta_1 x + \epsilon$

- What if $x$ contributes no information for predicting $y$? 

    - The mean of $y$ *does not* change as $y$ changes 
        - $\beta_1 = 0$

- We can *test the hypothesis* that $\beta_1 = 0$ 

- $H_0$: $\beta_1 = 0$

- $H_a$: $\beta_1 \neq 0$

![Screenshot from 2022-09-22 19-00-33](/home/tyansg/Repos/ANA500/Week 5/objects/Screenshot from 2022-09-22 19-00-33.png)

- The test statistic for the hypothesis test is found by considering the *sampling distribution* for $\hat{\beta}_1$ ) 

- Given the four assumptions made about $\epsilon$, $\hat{\beta}_1$ will have a sampling distribution that is normal with a mean of $\beta_1$) and a standard deviation of $\frac{\sigma}{\sqrt{(x - \bar{x})^2}}$ 

- $\sigma$ is typically unknown and must be estimated with $s$, therefore the sampling distribution will usually follow a *Student’s t-distribution* with $n – 2$ *df*. 

- t-stat = $\frac{\hat{\beta}_1 - \beta_{H_0}}{\frac{s}{\sqrt{\sum (s  -  \bar{x})^2}}}$

    

- E.g. Recall our estimates from the previous set of slides: 

- $\hat{y} = 10.43 + 2.03 x$ 

- $H_0$: $\beta_1 = 0$

- $H_a$: $\beta_1 \neq 0$

- $\sum (x - \bar{x})^2 = 296 $

- $\sqrt{296} = 17.2 $

- $SSE = \sum (y_i - \hat{y}_i)^2 = 27.78$

- $s = \sqrt{\frac{27.78}{5}} = 2.36$

- t-stat $= \frac{2.03 - 0}{2.36 / 17.2} = 14.79$

- p-value $= 0.000013$, reject $H_0$, there is a *linear* relationship between $y$ and $x$

    

- Confidence interval: $\hat{\beta}_1 \pm t_{\alpha/2} * (\frac{s}{\sqrt{(x - \bar{x})^2}})$

- E.g. continued: 95% confidence interval $= 2.03 \pm 2.57 ∗ (0.137)$

    - 95% confidence interval $= (1.68, 2.38)$ 

- A confidence interval can be used to test any hypothesis about $\beta_{1}$

    - If the value for $\beta_1$ specified in $H_0$ is not in the confidence interval, reject $H_0$.

    

- $\hat{\beta}_{1}$ provides and estimate of the linear relationship between $y$ and $x$.

- It can be difficult to determine the strength of the linear relationship due to differences in units of measurement. 

- Pearson correlation coefficient ($r$) can help. 

- $r = \frac{\sum_i (x_i - \bar{x}) (y_i - \bar{y})}{ \sqrt{ \sum_i (x_i - \bar{x})^2 \sum_i (y_i - \bar{y})^2 } }$

- $-1 \leq r \leq 1$ 

- $r$ provides essentially the same information as $\hat{\beta}_1$, the only real difference is the units of measurement.

    

- The coefficient of determination (R-squared) 

    - A sample statistic provided in almost all regression output

- We are interested in how much the errors in predicting $y$ are reduced when using the information provided by $x$. 

- If $x$ provides no information for predicting $y$, then the best estimate for $y$ is $\bar{y}$. 

    - In this case, $\sum_i (y_i - \bar{y})^2$ will be about the same as $\sum_i (y_i - \hat{y})^2$

- If $x$ does provides information for predicting $y$ then $\sum_i (y_i - \hat{y})^2$ will be smaller than $\sum_i (y_i - \bar{y})^2$.

    

- We can calculate the reduction in the sum of squared deviations as a percentage of $\sum_i (y_i - \bar{y})^2$

- R-squared $= \frac{\sum_i (y_i - \bar{y})^2 - \sum_i (y_i - \hat{y})^2}{\sum_i (y_i - \bar{y})^2} = 1 − \frac{\sum_i (y_i - \hat{y})^2}{\sum_i (y_i - \bar{y})^2}$ 

- E.g. continued: R-squared = $1 − \frac{27.78}{1244} = 0.978$ 

- $-1 \leq \text{R-squared} \leq 1$ 

- The sum of the squared deviations of $y$ around its predicted values is reduced by $97.8\%$ when using $\hat{y}$ to predict $y$ rather than $\bar{y}$. 

- Perhaps a more useful interpretation: approximately $97.8\%$ of the total variation in $y$ is explained by its linear relationship with $x$.

    

- Uses of regression model: 

    1. Estimate the mean of $y$ for a specific $x$ value 

        - E.g. What is mean sales for all restaurants that spend 400 on advertising? 

        - We are estimating the mean of $y$ for a large number of experiments at the given $x$ value. 

    2. Predict the value of $y$ given a specific $x$ value 

        - E.g. What is predicted sales for a single restaurant that spends 400 on advertising?
        - We are trying to predict $y$ of a single experiment at a given $x$ value. 

- The estimated mean and the predicted value of $y$ for a given $x$ value will always be the same, but estimation will always have more precision than prediction.

    

- $\hat{y} = \hat{\beta}_0 + \hat{\beta}_1 x$ is the model we use to estimate $\mathbb{E}(y)$ and to predict an individual value of $y$. 

- E.g. $\hat{y} = 10.43 + 2.03 x$

    - Estimate $\mathbb{E}(y)$ for $x = 20$  => $= 10.43 + 2.03(20) = 51.03 $
    - Predict $y$ for $x = 20$ => $= 10.43 + 2.03(20) = 51.03 $

- The difference in the two uses has to do with accuracy. 

    

- Let $x_p$ denote the $x$ value at which we are estimating and predicting. 

- Standard deviation of the sampling distribution of the estimator $\hat{y}$ of the mean value of $y$ at $x_p$ is called the *standard error* of $\hat{y}$

    - $\sigma_\hat{y} = \sigma \sqrt{ \frac{1}{n} + \frac{ (x_p - \bar{x})^2 }{ \sum_i (x_i - \bar{x})^2 } }$
    - $\sigma$ is the standard deviation of the error term. 

- The standard deviation of the prediction error for the predictor $\hat{y}$ of an individual $y$ value at $x_p$ is called the *standard error of prediction.* 

    - $\sigma_{\hat{y} - y} = \sigma \sqrt{1 + \frac{1}{n} + \frac{ (x_p - \bar{x})^2 }{ \sum_i (x_i - \bar{x})^2 } }$

