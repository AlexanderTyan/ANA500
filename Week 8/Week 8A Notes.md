$$
\newcommand{\pr}{\text{I\kern-0.15em P}}
\newcommand{\Ha}{H_a}
\newcommand{\Ho}{H_0}
\newcommand{\pv}{\text{p-value}}
\newcommand{\ss}{\sum_{i=1}^{n}}
$$


# Notes

## Week 8
### Module 4 Week 8A

#### Qualitative Dependent Variable and Logistic Regression

- It is not uncommon for the dependent variable of interest to be a dummy variable.

- E.g. how does income ( $x$ ) relate to whether someone votes ( $y$ )? 

- $y = \beta_0 + \beta_1 x_1 + \epsilon$

    - Where $y = 0$ if person did not vote and $y = 1$ if person did vote. 

- This is a linear model and can be fit to the data using least squares. 

    - This is known as the *linear probability model* 

- The predicted values ( $\hat{y}$ ) are interpreted as the *predicted probability that $y = 1$.*

    

- Suppose the linear probability model on the previous slide is estimated via least squares producing the following results: 

    - $\hat{y} = 0.07 + 0.02 x_1$
    - Interpretation of $\hat{\beta}_1$: when income increases by one-unit the predicted probability that someone votes increases by $0.02$. 
    - Strong points: simple model with easily-interpretable coefficients

- What is the predicted probability that someone with an income of $20$ votes? 

    - $\hat{y} = 0.07 + 0.02 (20) = 0.47$

- What is the predicted probability that someone with an income of 50 votes? 

    - $\hat{y} = 0.07 + 0.02 (50) = 1.07$
        - What does it mean for a probability to be greater than 1? This is nonsensical.
        - Main drawback of a linear model: predictions can fall outside of sensible probability values.

    

- ![lecture_1](objects/lecture_1.png)

    - Clearly, outcome variable is binary; only takes on values of $0$ or $1$
    - The prediction line demonstrates the drawback: predicting values outside of $0$ and $1$ for high and low $x$ values.  




- Problems arise using least squares when $y$ is a dummy variable. 

    1. Error term is not normally distributed (not a huge problem when the sample is large).
    2. Variance of error term is not constant  (also not a huge problem because available remedies: weighted least squares or calculating robust standard errors, to be seen in 510).
    3. Nonsensical predicted values (i.e. predicted probabilities)  (<- The main issue!)

- Using a *logistic regression model* (often called a *logit model*) is a common approach to help circumvent these problems, especially problem 3. 

- A logistic model uses a nonlinear functional form to force the predicted probabilities within the meaningful $(0, 1)$ range. 

- Following is a general overview: more to come later in the ANA program.

  ​    

- $\mathbb{E}(y) = \frac{e^{\beta_0 + \beta_1 x_1}}{1 + e^{\beta_0 + \beta_1 x_1}} = \mathbb{P}(y = 1) = \pi$

- $\mathbb{E}(y)$ cannot go below $0$ or above $1$ 

- This model is *nonlinear* in the parameters, and therefore, cannot be estimated via least squares.

- The model can be transformed into a linear one: 

    - $ln(\frac{\pi}{1 - \pi}) = \beta_0 + \beta_1 x_1$
        - This is known as a *“log-odds model”*
    - This approach (i.e. transforming and using least squares) is not recommended. 
        - The outcome is the log of probabilities in the population, where these probabilities are not observed
    - But helpful for coefficient interpretation:
        - Left-hand side: natural log of the odds of the event occurring (probability that the event occurs divided over the probability that it does not occur)
            - An event that has the same probability of occurring and not occurring has odds of $1$
            - If probability of occurring $>$ not occurring: odds are $> 1$
            - If probability of occurring $<$ not occurring: odds are $< 1$
        - => Estimated coefficient interpretation: estimated change in the log-odds from a one-unit increase in the predictor of interest
            - BUT: interpreting log-odds is not convenient => can still obtain an interpretation similar to the linear probability model, just need some computation help

- The standard approach is to estimate using *maximum likelihood*

  ​    

- ![lecture_2](objects/lecture_2.png)

    - Clearly, the S-curve (which becomes a reversed S-curve for a negative relationship)
    - The steepast part of the S-curve is always at $0.5$. 
    - Always between $0$ and $1$.
    - Logistic functions first developed to model population growth; popular in science applications.

      

- The estimated parameters in a logit model represent the change in the log-odds from a one-unit increase in $x$, holding other $x$'s constant. 

- Usually ( $e^{\hat{\beta_1}} - 1$ ) is calculated, to give the *percent change in odds from a one-unit increase in $x$.* 

- Example for model with two $x$'s: 

    -  $\hat{\beta}_1 = −0.7553 → e^{-.7553} - 1 = -0.53 $
        - For a one-unit increase in $x$, the odds decrease by 53%, holding $x_2$ constant. 
    -  $\hat{\beta}_2 = 0.33 → e^{0.33} - 1= 0.39 $
        - For a one-unit increase in $x_2$, the odds increase by 39%, holding $x_1$ constant. 

- *Marginal effects* can also be calculated which measure the change in the predicted probability that $y = 1$ from a one-unit increase in $x$.

- "Odds" are of the outcome variable being $1$ (event occuring).

  ​    

- Adequacy of the model can be tested.

- Model parameters are tested using Chi-squared tests. 

- Testing overall model adequacy (e.g. with two $x$'s) 

    - $\Ho$: $\beta_1 = \beta_2 = 0$
    - $\Ha$: at least one $\beta \neq 0$
    - Test statistic is Chi-squared with $k$ (i.e. # of $x$'s') *df*

- Testing individual parameters 

    - $\Ho$: $\beta_1 = 0$
    - $\Ha$: $\beta_1 \neq 0$
    - Test statistic is Chi-squared with 1 *df*

    

- There is no $R^2$ because the logit model is not linear. However, there are measures of fit. 

- For example: a number of Pseudo-$R^2$ measures; not the same interpretation as $R^2$.

- Classification tables help assess the usefulness of the model. 

    - Percentage of observations correctly classified. 
    - Correctly classified if $y = 1$ and $\hat{y} > 0.50$
        - *Sensitivity*: proportion of correct hits when $y = 1$
    - Correctly classified if $y = 0$ and $\hat{y} < 0.50$ 
        - *Specificity*: proportion of correct hits when $y = 0$
    - Whether Sensitivity/Specificity is high enough is an analyst's call
    - Other thresholds can be used instead of $0.50$

    

- ![lecture_3](objects/lecture_3.png)

- Correctly classified (overall) $= (9/12)*100 = 75$%

- Sensitivity $= (4/6) * 100 = 66.7$% 

- Specificity $= (5/6) * 100 = 83.3$%

- Important: to report both overall accuracy AND sensitivity/specificity because the outcome of interest can have an imbalance; having far more 1's or 0's. 

    - E.g. a model that always predicts less then $0.50$ would have high accuracy when there are a lot of $0$ values for the outcome; the fact of never correctly classifying $1$'s would be obscured without reporting Sensitivity.
