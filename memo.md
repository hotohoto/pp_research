# Memo

## Question

- Can we say frequentists' supervised models assume conditional independence on the target variable?
  - meaning they only assume comparatively plain structure between input variables?
- How to scale?
  - ADVI??

## TODO

- add questions section
- remove regularization term from mle code ??
- move bayesian network explanation as appendix
- try x data on uniform distribution
- read additional resources
  - cool!
    - [Hamiltonian Monte Carlo Sampler visualization](http://arogozhnikov.github.io/2016/12/19/markov_chain_monte_carlo.html)
  - pymc3
    - https://docs.pymc.io/nb_examples/index.html
    - https://twiecki.io/
  - pyro
    - https://canyon289.github.io/pages/InferenceCheatsheet.html
  - NUTS
    - https://wso2.com/blog/research/comparing-bayesian-and-classical-learning-techniques
- trutru
  - [MLE vs MAP](https://wiseodd.github.io/techblog/2017/01/01/mle-vs-map/)
  - [MLE vs MAP (한글)](https://niceguy1575.tistory.com/87)
  - [MLE with pdf](https://stats.stackexchange.com/questions/243283/in-mle-for-continuous-rv-why-is-it-ok-to-evaluate-a-pdf-at-a-point)
  - [MAP with pdf - 8](https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading13a.pdf)
  - show why MSE and regularization term
    - MLE and MAP

## etc

- If we can calculate the expectation value of posterior we can infer parameters.
- In high dimension every points are far.
- Random Walk doesn't scale well especially in high dimension
- data types
  - tall data
    - simple model with much data
  - wide data
    - complex model with a few data

## HMC: How to scale up

- let's guide a sampler using vector fields as trajectories.
  - like gravity make earth revolve around sun when the earth has a right amount of momentum.

=> "HMC"

- V
  - potential energy
- T
  - kinetic energy
  - needs to be tuned
- $\tau$
  - integration time
  - needs to be tuned
- $\epsilon$
  - step size
  - too large
    - rejects a lot
  - too small
    - accepts a lot
    - but still it's slow

## NUTS: How to tune HMC parameters

- T
- $\tau$
- $\epsilon$
  - define cost function

## how to find if our sampler is not working properly

- there can be bad region where it's hard to get out(??)

## how to pick prior distributions

- Normal distribution
  - good for slopes and intercepts
- Half Cauchy distribution
  - has less variance than the normal distribution
  - you may use this for the standard deviation which is a noise term (since we have less information about the noise than the slopes or the intercepts)
  - derived by taking non negative support of cauchy distribution and normalizing it
    - Cauchy distribution has heavy tails than Normal distribution

logistic function is inverse logit function

## additional resources

- https://docs.pymc.io/notebooks/getting_started
- https://ericmjl.github.io/bayesian-stats-talk/
- https://pymc-devs.github.io/pymc/modelfitting.html
- https://www.youtube.com/watch?v=-sIOMs4MSuA
- https://arviz-devs.github.io/arviz/examples/index.html
- https://ermongroup.github.io/cs228-notes/representation/directed/
