#Notes:
## Finite Sample Considerations
For the finite sample analysis, we will use the following tests:
- Wald's Test (W)
- Likelihood Ratio Test (LR)
- Score Test (Lagrange Multiplier Test) (LM)

Asymptotic nature of the tests show that under the null hypothesis, $W, LR, LM \overset{H_0}{\sim} \chi_r^2$ for $r$ degrees of freedom (i.e. the number of parameters in the model).

That is: 

$$
\begin{align*}
    W \overset{H_0}{\sim} \chi_r^2\\
    LR \overset{H_0}{\sim} \chi_r^2\\
    LM \overset{H_0}{\sim} \chi_r^2
\end{align*}
$$

That is nice, but do not usually have infinitely many datapoints. So, we need to consider the finite sample properties of these tests. The following relation holds. 

$$ W \geq LR \geq LM  \overset{H_0}{\sim} \chi_r^2$$

Thus, if we reject the null hypothesis under the LM test, we will also reject under the LR and W tests. 

We know that: 

$$\begin{align*} 
    P(\text{Reject } H_0 | H_0 \text{ is true}) = \alpha\\
    P(\text{Reject } H_0 | H_0 \text{ is false}) = 1 - \beta = \gamma
\end{align*}$$

Such that $\alpha$ is the Type I error rate and $\beta$ is the Type II error rate, and $\gamma$ is the power of the test.

We also know that the trade-off between Type I and Type II are inversely related. Now for our tests in mind, we have the following relations:

$$
\begin{align}
    \alpha_W \geq \alpha_{LR} \geq \alpha_{LM}\\
    \gamma_W \geq \gamma_{LR} \geq \gamma_{LM}
\end{align}
$$

- Which means that for eq. 1, we would want to use the LM statistic, since we would reject the null hypothesis fewer times under this staistic.

- Likewise, for eq. 2 we would want to use the W statistic, since we would reject the null hypothesis more times under this statistic.

If the $\alpha$ (size of critical region) of the statistical test which is important to you, then you would want to use the LM test. If the $\gamma$ (power of the test) is important to you, then you would want to use the W test.
