Rosner, Bernard. "Fundamentals of Biostatistics." 8th Edition
============================================================

Table of Contents: 

- 4.10 the Poisson distribution / 90

- 4.11 Computation of Poisson Probabilities / 93

- 4.12 expected value and variance of the Poisson distribution / 95

- 4.13 Poisson Approximation to the Binomial distribution / 96

- 5.8 normal Approximation to the Poisson distribution / 135 

- 6.9 estimation for the Poisson distribution / 189 

- 7.11 one-Sample inference for the Poisson distribution / 251

- 8 Confidence Limits for the expectation of a Poisson variable (μ) / 827

Notes 4.10 the Poisson distribution / 90
------------------------------------
- The Poisson distribution is a discrete probability distribution that expresses the probability of a given number of events occurring in a fixed interval of time or space. Usually associated with rare events, and is perhaps the second most used after the binomial distribution.
- Rare events over time, and over surface area are common applicaitons of the Poisson distribution.

Assumptions 4.1:
1. the prob. of observing 1 death is directly proportional to the length of time in the interval $\Delta t$. i.e. $P(1 death) \approx \lambda \Delta t$ for some constant $\lambda$.
2. the prob. of observing 0 deaths over $\Delta t$  is approximately $1-\lambda \Delta t$. 
3. The prob. of ovserving more than 1 death over this time interval is essentially 0.


Assumptions 4.2:  
**Stationary**: Assume the number of deaths per unit time is the same throughout the entire interval. Thus an increase in the indicent of the disease as time goes on within the time period $t$ would violate this assumption. Notice that $t$ should not be overly long because this assumption is less likely to hold as $t$ increases.

Assumption 4.3:
**Independence**: If a number of deaths occur within one time subinterval, then it has no bearing on the probability of death in the next time subinterval. Would be violated in epidemic situations if a new case of the disease occurs, then subsequent dealths are likely to build up over a short period of time until after the epidemic subsides.

Formal Equation 4.8:
The probability of observing $k$ events occuring in a time period of $t$ for a Poisson r.v. with parameter $\lambda$ is

$$P(X=k) = \frac{e^{-\lambda}(\lambda)^k}{k!} \quad k = 0,1,2,\dots$$ 

where $\mu = \lambda t$ and $e$ is the base of the natural logarithm.

- $\lambda$ the expected number of events over a time period $t$, and the difference between the Poisson and binomial distribution concerns the number of trials and events. Binomial distribution has finite $n$ trials, and the Poisson distribution has indefinitely large. 

Notes on 4.12 Expected Value and Variance of the Poisson Distribution / 95
-------------------------------------------------------------------------

- an important guideline in which to identify r.v.s that follow a Poisson distribution is stated: 
  
  For a Poisson distribution with parameter $\mu$ the mean and variance are both equal to $\mu$.

- This is quickly identifiable of a Poisson dist. 

Notes on 4.13 Poisson Approximation to the Binomial Distribution / 96
---------------------------------------------------------------------
- An important use for the Poisson distribution is as an approximation to the binomial distribution. Consider for llarge $n$ and small $p$, the mean of this distribution is $\mu = np$ and the variance is $\sigma^2 = np(1-p) = npq$. Note that $q \approx 1$  for small $p$ and thus $npq \approx np$. Almost equal in this case suggesting the following. 
  
  Poisson Approximation to the Binomial Distribution: The binomial distribution with large $n$ and small $p$ can be accurately approximated by a Poisson distribution with parameter $\mu = np$.

- The notation for a binomial dist. requires ($n$ choose $k$), $P(X=k)$ which can be cumbersome for large $n$. 

- A conservative rule for how large $n$ and $p$ should be is: $n \geq 100$ and $p \leq 0.1$.

Notes on 5.8 Normal Approximation to the Poisson Distribution / 135
-------------------------------------------------------------------
- The normal dist. can be used to approximate discrete distributions other than the binomial, such as the Poisson. The primary motivation is that the Poisson distribution is cumbersome to use for large $\mu$. 
- Same technique is used for the binomial distribution; the mean and variance of the Poisson distribution and the approximating normal distribution are equated.

Equation 5.16: 
A Poisson distribution with parameter $\mu$ is approximated by a normal distribution with mean and variance both equal to $\mu$. $P(X = x)$ is approximated by the area under $N(\mu,\mu)$ density from $x - \frac{1}{2}$ to $x + \frac{1}{2}$ for $x = 0$. This approximation is used when $\mu \geq 10$.

Notes on 6.9 Estimation for the Poisson Distribution / 189
---------------------------------------------------------
- Following the example, let $X$ be the number of children who developed leukemia in Woburn during the 1970s. $X$ represents a rare event, we assume it follows a Poisson distribution with parameter $\mu = \lambda T$. We know, $E(X) = \lambda T$ where $T$ is time, and $\lambda$ is the number of events per unit time.

- A **person-year** is a unit of time defined as 1 peerson being followed for 1 year. 

- The **incidence rate** is the number of new cases of a disease that occur during a specified period of time in a population at risk for developing the disease. The incidence rate is often expressed as the number of new cases per 100,000 person-years.

Equation 6.22: Point Estimation of for the Poisson Distribution
- Assume that the number of events $X$ over $T$ person-years is Poisson distributed with parameter $\mu = \lambda T$. An unbiases estimator of $\lambda$ is given by $\hat{\lambda} = X/T$ where $X$ is the number of events over $T$ person-years.
- If $\lambda$ is the incidence rate per person-year, $T$ = the number of person-years of follow-up and we assume that a Poisson distribution for the number of events $X$ over $T$ person-years, then the expected value of $X$ is given by $E(X) = \lambda T$ Therefore,
$$E(\hat{\lambda}) = E(X) / T = \lambda T/T = \lambda$$

Thus, $\hat{\lambda}$ is an unbiased estimator of $\lambda$.


Interval Estimation: 
- How to obtain interval estimate for $\lambda$? Use similar techniques as for the binomial distribution of $p$. First, obtain CI for $\mu$ = expected number of events over time $T$ of the form $(\mu_1,\mu_2)$ then obtain corresponding CI for $\lambda$ from $(\mu_1/T,\mu_2/T)$.

Exact Method for Obtaining CI for the Poisson Parameter $\lambda$:

An exact $100%(1-\alpha)$ CI for the Poisson parameter $\lambda$ is given by $(\mu_1/T, \mu/T)$ where $\mu_1$ and $\mu_2$ satisfy the equations:

$$\begin{align}
    P(X \leq x | \mu = \mu_1) &= \frac{\alpha}{2}\sum_{i=1}^{\infty}e^{-\mu_1}\frac{\mu_1^k}{k!}\\
    P(X \leq x | \mu = \mu_2) &= 1 - \frac{\alpha}{2}\sum_{i=1}^{\infty}e^{-\mu_2}\frac{\mu_2^k}{k!}\\
\end{align}$$

and $x$ = the number of observed events, $T$ = the number of person-years of follow-up, and $\alpha$ = the desired level of significance.

Notes on 7.11 One-Sample Inference for the Poisson Distribution / 251
---------------------------------------------------------------------

- Study: Analysing the hazards faced by rubber workers. 8418 white male workers between ages 40-84 (both retired and not), followed for 10 years on Jan. 1st, 1964. Mortality rates compared to the U.S. white male mortality rates in 1968. One finding showed 4 deaths due to Hodgekin's disease were observed compared with the 3.3 deaths from U.S. mortality rates. Is this significant?

Assume $p$ is constant for all people in the sampele. Let $X$ be the total number of deaths for members of the study population. And let $p_i$ be the probability for the $i$th individual. 

Under the null hypothesis the death rates for the study population are the same for those in the general U.S. population, therefore $\mu_0 = \sum_{i=1}^{n}p_i$

If the disease in the study is considered rare, then the obs. number may be approximately equal to the Poisson distribution with the unknown mean of $\mu$.

$$
\begin{align*}
    H_0: \mu &= \mu_0\\
    H_1: \mu &\neq \mu_0
\end{align*}
$$

If we use the critical value approach to a significance test of the null hypothesis, suppose the crirical region is $(c_1, c_2) \Rightarrow c_1 < \mu_0 < c_2$ we would accept $H_0$. Otherwise, if $\mu_0 < c_1$ or $\mu_0 > c_2$ we would reject $H_0$.

#### One Sample Inference for the Poisson Distribution (Small-Sample Test Critical-Value Method):
Let $X$ be a Poisson r.v. with parameter $\mu$. To test the hypothesis $H_0: \mu = \mu_0$ against $H_1: \mu \neq \mu_0$ using a two-sided test with significance level $\alpha$ 
1. Obtain the two sided critical region $100%(1-\alpha)$ for $\mu$ based on the obs. value $X$. Denote CI as $(c_1, c_2)$
2. If $\mu_0 < c_1$ or $\mu_0 > c_2$ reject $H_0$. If $c_1 \leq \mu_0 \leq c_2$ accept $H_0$.

#### Using the p-value method

Wish to rejec $H_0$ if $x$ is either much larger or much smaller than $\mu_0$. 

#### One Sample Inference for the Poisson Distribution (Small-Sample Test-- p-value Method):

Let $\mu$ the parameter of a Poisson distribution. To test the hypothesis $H_0: \mu = \mu_0$ against $H_1: \mu \neq \mu_0$ using a two-sided test with significance level $\alpha$:

1. Compute $x$  = the number of deaths observed in the study population.
2. Under $H_0$, the r.v. $X$ will follow a Poisson distribution with parameter $\mu_0$. Thus, the exact two-sided p-value is given by:

$$
\begin{align*}
    \min\left( 2* \sum_{k=0}^{x} \frac{e^{-\mu_0} \mu_0^k}{k!}, 1\right) \quad \text{if } x \leq \mu_0\\
    \min\left( 2* \sum_{k=x}^{x-1} \frac{e^{-\mu_0} \mu_0^k}{k!}, 1\right) \quad \text{if } x \leq \mu_0\\
\end{align*}
$$

#### One-Sample Inference for the Poisson Distribution (Large-Sample Test):

Let $\mu$ be the parameter of a Poisson distribution. To test the hypothesis $H_0: \mu = \mu_0$ against $H_1: \mu \neq \mu_0$. 
1. Compute $x$ = the number of deaths observed in the study population.
2. Compute the test statistic: 
   $$ X^2 = \frac{(x - \mu_0)^2}{\mu_0} = \mu_0\left( \frac{SMR}{100} -1 \right) ~ \chi_1^2 \quad \text{ under } H_0
    $$
    - where $SMR$ is the standardized mortality ratio, and $\chi_1^2$ is a chi-squared r.v. with 1 degree of freedom.
3. For two-sided test at level $\alpha$, $H_0$ is rejected if $$X > \chi_{1,1-\alpha/2}^2$$ and accepted if $$X \leq \chi_{1,1-\alpha/2}^2$$
4. The exact p-value is given by $Pr(\chi_1^2 > X^2)$
5. Test should only be used if $\mu_0 \geq 10$.
6. an approximate $100%(1-\alpha)$ CI for $\mu$ is given by $x \pm z_{\alpha/2}\sqrt{x}$



