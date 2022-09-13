$$
\newcommand{\pr}{\text{I\kern-0.15em P}}
\newcommand{\Ha}{H_a}
\newcommand{\Ho}{H_0}
\newcommand{\pv}{\text{p-value}}
\newcommand{\ss}{\sum_{i=1}^{n}}
$$


# Notes

## Week 4
### Module 2 Week 4B
#### Chi-Squared
- The Chi-squared distribution is a member of the normal family of distributions and often arises as the sampling distribution for a test statistic. 

- We will use the Chi-squared distribution for: 
    - Goodness of fit tests
    - Tests of independence
    - Tests of homogeneity
    - Tests of a single variance
    
- A Chi-squared distribution has a mean equal to $df$ and standard deviation equal to $\sqrt{2df}$ 

- A Chi-squared random variable with $k$ degrees of freedom is the sum of $k$ independent, squared standard normal distributions.

- A Chi-squared distribution is *skewed to the right* and the skew decreases as $df$ increases.




##### Goodness of fit test 

- Do the data fit a particular distribution?

- Often used for *categorical data*

- $\Ho$: data fit the expected distribution 

- $\Ha$: data do not fit the expected distribution

- The test involves comparing expected frequencies ($E$) with observed frequencies ($O$).

- Let $k =$ the number of categories of the variable of interest

- Test statistic $= \sum_k \frac{(O - E)^2}{E}$

- $df = k – 1$


- E.g. The following table shows the distribution of grades a professor expects in a class of 100 students as well as the grades she observes.

    - ![Screenshot from 2022-09-12 19-46-36](files/Screenshot from 2022-09-12 19-46-36.png)
    
    - Test-stat $= 4.05 + 2.13 + 4.8 + 0.90 + 6.4 = 18.28$
    - $df = k – 1 = 5 – 1 = 4$
    - $\pv = 0.0011$
    - $0.0011 < 0.05$ => reject $\Ho$, the observed grades do not fit the expected distribution



##### Test of independence 

- Are two variables independent? 

- Often used for *nominal variables* 

- $\Ho$: the two variables are independent 

- $\Ha$: the two variables are not independent 

- Test statistic $= \sum_k \frac{(O - E)^2}{E}$

- $df = (\text{number of rows} – 1)\times (\text{number of columns} – 1)$

- Expected frequencies ( $E$ ) won’t always be obvious.

    - Calculate using $\frac{(\text{row total}) \times (\text{column total})}{(\text{total number of observations})}$  
    - Row and column totals are often referred to as row and column *marginals*

    

- E.g. Is there a relationship between gender and being a STEM major?

    - ![Screenshot from 2022-09-12 20-03-33](files/Screenshot from 2022-09-12 20-03-33.png)

    - $\text{Test-stat} = 0.27 + 0.26 + 0.11 + 0.10 = 0.74$

    - $df = (2 – 1) \times (2 – 1) = 1$ 

    - $\pv = 0.39$ 

    - $0.39 > 0.05$ => fail to reject $\Ho$, gender and being a STEM major are independent
