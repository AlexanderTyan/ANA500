# Notes
## Week 3
### Module 2 Week 3A
#### Point Estimation and Confidence Intervals
- I.e. how to quantify uncertainty of estimates?

##### Point Estimation
- E.g.:
  - What is the mean price of a 4-star hotel room in Washington DC?
    - Gather data (e.g. internet search of prices) -> calculate average price
      - This is a *point estimate* of a population mean
  - How often are flights delayed?
    - Gather data (e.g. record the flights that are delayed) à divide by the total
    number of flights.
      - This is a *point estimate* of a population proportion
- **Inferential Statistics** - using a sample of data to make predictions about
population parameters of interest

##### Confidence intervals
- The *Point Estimate* - unlikely to be exactly equal to the true value of
the parameter of interest, we hope it is close though.
  - A **confidence interval** - quantifies this uncertainty.
- A *confidence interval*, like other sample statistics, is a *random
variable*, it is not fixed. (*Population Parameter* is fixed).
- E.g. Back to the hotel room example. A (random) sample of data is
collected. The sample mean is calculated. We would like to know the
population *standard deviation* ($\sigma$), but it is often unknown. The
sample standard deviation ($s$) can be calculated. With this information
a *confidence interval* for the estimated mean can be calculated. It changes with the *Random Sample*.

- A *confidence interval* provides a range of values it is reasonable for the
*population mean (parameter)* to fall in.
  - There is no guarantee that the interval contains the true value of the parameter.
  - We can make probability statements about how likely it is.
- Recall that $\bar{X} \sim (\mu, \frac{\sigma^2}{n})$
  - *About 95% of all observations fall within 2 standard deviations of the mean.* I.e. about 95% of all sample means must fall within 2 *standard deviations* of $\mu$
- E.g. suppose $\bar{X} = 290$ and $\sigma = 200$ (i.e. the *population SD* is known here) and $n = 100$
  - *Standard deviation* for $\bar{X} = \frac{\sigma^2}{n} = \frac{200}{\sqrt{100}} = 20$
  - 2 standard deviations $= 40$
  - 95% *confidence interval* -> $290 \pm 40 = (250, 330)$
    - *We are 95% confident the population mean falls in this interval* (In reality it might not be, but probability that it doesn't is only $5\%$).

- *Confidence Intervals* form:
  - *Point Estimate* $\pm$ *Margin of Error*
    - *Margin of error* depends on *level of confidence* and the *standard deviation of the
  estimate* (i.e. *standard error*)
- *Interpretation*: The **Confidence Level** is *the percentage of times the interval contains the true parameter value in repeated random samples*.
- $\alpha = (1 – \text{level of confidence}) = \text{level of significance}$

