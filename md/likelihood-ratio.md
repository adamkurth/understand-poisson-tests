Likelihood Ratio Test Guide
---------------------------


### Introduction

The usual setting to learn Likelihood Ratio Test (LRT)/LR statistic is evaluting under the simple null hypothesis. Suppose that the parameter $\theta_0$ is the value of the parameter under the null hypothesis, and $\hat{\theta}$ is the MLE estimate of the parameter in question. The likelihood ratio test is a statistical test which measures the ratio of the two likelihood functions. 

<p align="center">
  <img width="400" height="250" src="https://stats.idre.ucla.edu/wp-content/uploads/2016/02/nested_tests.gif">
</p>

Visually, this ratio can be understood as the proportion of the heights of the two likelihood functions evaluated at each $\theta_0, \hat{\theta}$, where the likelihood function is the probability of the observed data given the parameter. 

$$
\begin{align*}
  \ell_0 &= L_0(x_1,\cdots, x_n; \theta_0) = \prod_{i=1}^{n} f(x_i|\theta_0) \\
  \ell_1 &= L_1(x_1,\cdots, x_n; \hat{\theta}) = \prod_{i=1}^{n} f(x_i|\hat{\theta})
\end{align*}
$$

To perform the LRT, we choose a constant $c$ such that the likelihood ratio test statistic $\lambda$ is defined as:

$$
\begin{align*}
  \lambda &= \frac{\ell_1}{\ell_0} = \frac{L_1(\hat{\theta})}{L_0(\theta_0)} =\frac{\max_{\theta} L(\theta)}{\max_{\theta \in \Theta_0} L(\theta)} \\
\end{align*}
$$

where $\Theta_0$ is the parameter space under the null hypothesis. 

Under the LRT, if $\lambda > c$, we reject the null hypothesis, and if $\lambda \leq c$, we fail to reject the null hypothesis. The value of $c$ is chosen such that the Type I error rate is controlled at a certain level, usually $\alpha = 0.05$. This test statistic is a measure of how much more likely the data are under the alternative hypothesis than under the null hypothesis.


### Generalized Likelihood Ratio Test

Suppose that the tests are not simple.
Let $S$ be the set of all possible values for the parameter $\theta$, suppose too that we can partition this set into two disjoint sets $S_0$ and $S_1$ such that $S_0 \cup S_1 = S$ and $S_0 \cap S_1 = \emptyset$. Therefore the test is defined as:

$$
\begin{align*}
  H_0: \theta \in S_0 \\
  H_1: \theta \in S_1
\end{align*}
$$

Find the likelihoods corresponding to the most likely values of $\theta \in S_0$ and $S$ respectively. As before we define the likelihoods as: 

$$
\begin{align*}
  \ell_0 &= \sup\{ L(x_1, \cdots, x_n; \theta) \mid \theta \in S_0 \}\\
  \ell_1 &= \sup\{ L(x_1, \cdots, x_n; \theta) \mid \theta \in S \}\\
\end{align*}
$$

We still choose a constant $c \in [0,1]$ such that the generalized likelihood ratio test statistic $\Lambda$ is defined as:

$$
\begin{align*}
  \Lambda &= \frac{\ell_1}{\ell_0} = \frac{\sup\{ L(x_1, \cdots, x_n; \theta) \mid \theta \in S_0 \}}{\sup\{ L(x_1, \cdots, x_n; \theta) \mid \theta \in S \}} \\
\end{align*}
$$

Under the GLRT, if $\Lambda > c$, we reject the null hypothesis, and if $\Lambda \leq c$, we fail to reject the null hypothesis. The value of $c$ is chosen such that the Type I error rate is controlled at a certain level, usually $\alpha = 0.05$.

Another formulation of LRT/GLRT where $LR$ is the statistic, is defined as:
$$
\begin{align*}
    LR &= -2( \log \mathcal{L}(\hat{\theta}_{MLE})  - \log \mathcal{L}(\theta_0)  ) \overset{H_0}{\sim} \chi^2_{df}\\
    &= -2( \ell(\hat{\theta}_{MLE})  - \ell(\theta_0)  ) \overset{H_0}{\sim} \chi^2_{df}\\
\end{align*}
$$

$$ 
\begin{align*}
    H_0: \theta = \theta_0 \\ 
    H_1: \theta > \theta_0
\end{align*} 
$$

Different from the previous formulation, this formulation is used when the null hypothesis is not simple. The test statistic is the difference between the log-likelihood of the MLE and the log-likelihood of the null hypothesis. This difference is then compared to a $\chi^2$ distribution with degrees of freedom equal to the difference in the number of parameters between the null and alternative hypotheses.

The exact same intuition applies. 

### Asymptotic Properties
The test statistic, $LR$ is asymptotically distributed as a $\chi^2$ distribution with degrees of freedom equal to the difference in the number of parameters between the null and alternative hypotheses.


#### Use Case (Nested Models)
When examining a model which is "nested", the LRT is a powerful test to compare the two models. Suppose the simpler model $s$ has fewer parameters than the model $g$. When testing whether the more complex model $g$ is significantly better than the simpler model $s$, the LRT compares the two, and expresses them in terms of deviance: 

$$
\begin{align*}
    LR &= -2( \log \mathcal{L}_s  - \log \mathcal{L}_g)\\
    &= -2 \log\mathcal{L} + 2 \log\mathcal{L}_s\\
    &= \text{deviance}_s - \text{deviance}_g\\
\end{align*}
$$

Given the trivial hypothesis test, $H_0: p_1 = p_2 \equiv p$ vs. $H_1: p_1 \neq p_2$, computing the MLE under both: 
$$
\begin{align*}
    D_s &= -2 \log \mathcal{L}(\hat{p}) \quad K_s = 1 \text{ number of params}\\
    D_g &= -2 \log \mathcal{L}(\hat{p}_1, \hat{p}_2) \quad K_g = 2 \text{ number of params}\\
\end{align*}
$$
Finally the $LR = D_s - D_g$ $df = K_g - K_s = 1$. Therefore the test statistic is $LR \sim \chi^2_1$.



--- 

#### References

- [8.4.5 Likelihood Ratio Tests](https://www.probabilitycourse.com/chapter8/8_4_5_likelihood_ratio_tests.php)

- [Likelihood Ratio Tests](https://sites.warnercnr.colostate.edu/gwhite/wp-content/uploads/sites/73/2017/04/LikelihoodRatioTests.pdf) 

- [Illustrate deriving the likelihood ratio test for rate of Poisson](https://mediaspace.baylor.edu/media/Illustrate+deriving+the+likelihood+ratio+test+for+rate+of+Poisson/1_blh70yxu)

- [Likelihood ratio test - introduction](https://www.youtube.com/watch?v=Tn5y2i_MqQ8&list=PLwJRxp3blEvb7P-7po9AxuBwquPv75LjU&index=47)

- [L2.3 LR, Wald, and Score Tests](https://www.youtube.com/watch?v=6N-dvmth5JI)

