# Notes
## Week 2
### Module 1 Week 2B
#### Continuous Random Variables and the Normal Distribution
##### Random Variables
- A **Continuous Random Variable** can take on any value in an interval
- The probability of any single value is *zero*
- **Probability Density Function (PDF)**
  - The probability of a random variable takes on a value between $a$ and $b$
    - Equal to the area under the *PDF* between $a$ and $b$ (via *Integration*)
- **Cumulative Distribution Function (CDF)**
  - The probability a random variable will take on a value equal to or less than
  some value.
    - Equal to the area under the CDF to the left of the value of interest.
- **Uniform Distribution (Continuous)**
  - All outcomes are equally likely
- $X \sim U(a, b)$  

$$
\begin{equation} 
  f(x) = \begin{cases} 
    \frac{1}{b - a}, & \text{for $x \in (a, b)$} \\ 
    0, & \text{otherwise}
  \end{cases}
\end{equation} 
$$

- **Mean** $= \frac{1}{2} (a + b)$
- **Variance** $= \frac{1}{12} (b - a)^2$
  