# Notes
## Week 2
### Module 1 Week 2A
#### Probability and Random Variables
- *Probability Theory* - important in linking *Samples* to underlying 
  *Population* of Interest => important for *Statisticsl Inference*.
##### Probability
- Values taken on by the variables are not known until they are observed. 
- Data is composed of observations of underlying *Random Variables*.
- *Probability Theory* provides the mathematics of this randomness.
- **Probability** - fraction of occurrences an event occurs over many 
  repeated trials. 
  - E.g. The probability of a coin flip coming up heads is the fraction of
    heads that occurs after many, many flips.
  - Note the long-run/repeated trial nature of the concept.
  - This is a *Frequentist* interpretation of *Probability*, adopted in this 
    class. 
    - Limitation: need for an objective/repeatable experiment.
    - Alternative: *Bayesian Probability* which views Probabilities as a 
      plausible expectation that an event occurs, which can updated as more 
      information becomes available (critiques cite its subjective nature).
  - Terminology (using the coin flip example):
    - **Experiment** - flipping of the coin.
      - is repeated and conducted under controlled conditions.
    - **Outcome** - result of a single experiment; not known until the coin 
      is flipped; there's a chance involved.
    - **Sample Space** ( $S$ ) ( $\neq$ *Sample* from a *Population*) - all 
      possible outcomes; e.g. $S = {H, T}$
    - **Event** - any combination of outcomes.
      - Denoted with upper-case letters. E.g. $A$ - event of Heads, then $P(A)$ - *Probability* of Heads.
      - $0 \leq P(A) \leq 1$
      - **Law of Large Numbers** - as the number of trials increases, the 
        *empirical* fraction of occurrences gets closer and closer to the 
        theoretical probability of occurrence; e.g. for an unbiased coin, 
        there more flips you observe, the fraction of tails or heads will 
        get closer to $0.5$.
- **Probability Rules**:
  - “and”: an outcome is in event $A$ and $B$ if it is in $A$ and $B$ at the 
    same time.
  - $A = {1, 2, 3, 4, 5, 6}$.
  - $B = { 4, 5, 6, 7, 8}$.
  - $A$ and $B$ $= A \cap B = {4, 5, 6}$.
  - “or”: an outcome is in event $A$ or $B$ if it is in $A$ or $B$.
  - A or B $= A \cup B = {1, 2, 3, 4, 5, 6, 7, 8}$
  - The complement of event $A$ is denoted $A'$
  - $P(A’) = 1 – P(A)$ 