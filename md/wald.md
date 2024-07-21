General Wald Test Guide
-----------------------

Introduction
-------------

When comparing the parameters $\theta_0, \hat{\theta}$, the Wald test is a statistical test that compares the difference between the estimated parameter $\hat{\theta}$ and the hypothesized parameter $\theta_0$ to the standard error of the estimated parameter. The test statistic is then compared to a $\chi^2$ distribution to determine the significance of the parameter.

This can easily be applied to means, regression coefficients, or any other parameter of interest. The Wald test is a general test that can be used to test the significance of a single parameter, multiple parameters, or a set of parameters in a statistical model.

<p align="center">
  <img width="400" height="250" src="https://stats.idre.ucla.edu/wp-content/uploads/2016/02/nested_tests.gif">
</p>

Visually, this is understood as seeing the difference along the parameter $\theta$ axis (x-axis) vs. the log-likelihood function (y-axis). The Wald test is a measure of how far the estimated parameter $\hat{\theta}$ is from the hypothesized parameter $\theta_0$ relative to the standard error of the estimated parameter.

Uses of Wald Test
-----------------
1. **Parameter Estimation**: Often used to test the hypotheses about the parameters (mean or regression coefficients) of a statistical model. Testing the equality of teo means $\mu_1$ and $\mu_2$ is a common example.
2. **Comparing Two Means**: Used frequently to compare the means of two groups, populations, or treatments. Such as comparing the mean incidence rate of a disease in two different populations.
3. **Regression Analysis**: Used to test the significance of individual predictors in a regression model. For example, in a multiple regression model, the Wald test can be used to test the significance of each predictor variable.

### Test Statistic
$$ W_T = \frac{(\hat{\theta} - \theta_0)^2}{1/I_n(\hat{\theta})} = \frac{(\hat{\theta} - \theta_0)^2}{I_n(\hat{\theta})^{-1}} = I_n(\hat{\theta}) (\hat{\theta} - \theta_0)^2 $$
Where:
- $\hat{\theta}$ is the estimated parameter (Maximum Likelihood Estimate, MLE) derived from the sample data.
- $\theta_0$ is the parameter under the null hypothesis.
- $I_n(\hat{\theta})$ is the expected Fisher information evaluated at the MLE. Measures the amount of information that the sample provides about the parameter.
- If $I_n(\hat{\theta})^{-1}$ is a single parameter, then $I_n(\hat{\theta})^{-1} = \text{Var}(\hat{\theta})$.
- $W_T$ is the Wald test statistic to which under the approximation to a $\chi^2$ we can then assess the significance of the parameter.

### Asymptotic Properties
- $W_T \sim \chi_1^2$ for a single parameter $\theta$, and for multiple parameters (i.e. vector $\theta$), $W_T \sim \chi_r^2$ where $r$ is the number of restrictions/dimensions.
- **Consistency**: As the sample size $n \rightarrow \infty$, the estimator $\hat{\theta} \rightarrow \theta$, converges in probability to the true parameter $\theta$.
- **Normality**: For large samples, the distribution of the test statistic $W_T \overset{d}{\rightarrow} \chi_1^2$ distribution $W_T \sim \chi_1^2$ asymptotically.
- **Efficiency**: The Wald's Test is asymptotically efficient, meaning it makes full use of available information in the data. 
- The Wald test, LRT, and Lagrange Multiplier (Score Test) are asymptotically equivalent as sample sizes approach infinity ($n \rightarrow \infty$).

### Confidence Interval
Using the normal approximation, the Wald test can be used to construct a confidence interval for the parameter $\theta$.

$$ CI = \hat{\theta} \pm z_{\alpha/2} \sqrt{\text{Var}(\hat{\theta})} $$

### Finite Sample Properties
$W_T \sim \chi_2^2$ asymptotically.

### Why Use Wald Test?
- **Large Sample Size**: The Wald test is powerful for large sample sizes due to the reliance on asymptotic normality of the estimator.
- **Parameter Magnitude**: The power of the test increases with the magnitude of the parameter under consideration. Large differences between the $H_0$ and $H_1$ lead to higher power.
- **Effect Size**: The test is more powerful when the effect size is large, making it easier to detect deviations from the null hypothesis.

### Why not to use Wald Test?
- **Small Sample Size**: 
  - **Limitation**: The normality assumption may not be valid for small samples, leading to inaccurate results.
  - **Impact**: Increase Type I and Type II error rates in small samples.

- **Distributional Assumptions**: 
  - **Limitation**: Requires the assumption that the estimator follows a normal distribution, which might not be true in practice.
  - **Impact**: Misleading results if the underlying distribution assumptions are violated.

- **Parameter Boundaries**: 
  - **Limitation**: Problems can arise when testing the boundaries of the parameter space.
  - **Impact**: The Wald test may have poor performance or be invalid.
  

---

Comparison of Two Poisson Distribution Means/Rates
---------------------------------------------------

Under the Null Hypothesis testing framework, when comparing whether the mean rates of two Poisson distributions,
$$
\begin{align*}
    H_0: \lambda_1 = \lambda_2 \\
    H_1: \lambda_1 \neq \lambda_2
\end{align*}
$$

Supposing the univariate case: For two independently distributed Poisson r.v. $X_1 \sim \text{Poisson}(\lambda_1)$ and $X_2 \sim \text{Poisson}(\lambda_2)$. The estimates of the sample mean the rates are $\hat{\lambda}_1$ for $n_1$ samples and $\hat{\lambda}_2$ for $n_2$ samples.

Thus, the difference of the sample means can be denoted as $\hat{delta} = \hat{\lambda}_1 - \hat{\lambda}_2$, and the standard error of the difference is given by: 
$$
\begin{align*}
    SE(\hat{\delta}) = \sqrt{\frac{\hat{\lambda}_1}{n_1} + \frac{\hat{\lambda}_2}{n_2}}
\end{align*}
$$

Using the Wald's test statistic $W_T$, the test statistic is given by:
$$
\begin{align*}
    W_T = \frac{(\hat{\lambda}_1 - \hat{\lambda}_2)^2}{\frac{\hat{\lambda}_1}{n_1} + \frac{\hat{\lambda}_2}{n_2}}
\end{align*}
$$
Such that the denominator is the variance of the difference of the sample means.

The test statistic $W_T$ follows a $\chi_1^2$ distribution under the null hypothesis, and the p-value can be calculated as:
$$
\begin{align*}
    p = 1 - \text{pchisq}(W_T, df = 1)
\end{align*}
$$

Considerations
--------------
1. **Sample Size**: Ensure that the sample sizes $n_1$ and $n_2$ are large enough to use the asymptotic properties of the Wald test.
2. **Poisson Assumption**: Verify that the data from both groups follow a Poisson distribution. This can be checked by examining if the mean and variance are approximately equal.
3. **Independence**: Ensure that the observations in the two groups are independent of each other.
**
### References
- [Rosner, Bernard. "Fundamentals of Biostatistics." 8th Edition.](https://statanaly.com/wp-content/uploads/2023/04/Fundamentals-of-Biostatistics-7th-Edition.pdf)

- [Statistics How To](https://www.statisticshowto.com/wald-test/)

- [Wald Test Introduction](https://www.youtube.com/watch?v=TFKbyXAfr1M)

- [Wald Test explained](https://www.youtube.com/watch?v=WNpHK5lCJwY)

- [Wald Test | Likelihood Ratio Test | Score Test](https://www.youtube.com/watch?v=yzO80fa0_Y4)
**