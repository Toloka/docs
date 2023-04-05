# GLAD
`crowdkit.aggregation.classification.glad.GLAD` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/glad.py#L24)

```python
GLAD(
    self,
    n_iter: int = 100,
    tol: float = 1e-05,
    silent: bool = True,
    labels_priors: Optional[Series] = None,
    alphas_priors_mean: Optional[Series] = None,
    betas_priors_mean: Optional[Series] = None,
    m_step_max_iter: int = 25,
    m_step_tol: float = 0.01
)
```

The **GLAD** (Generative model of Labels, Abilities, and Difficulties) model is a probabilistic model that parametrizes the abilities of workers and the difficulty of tasks.


Let's consider a case of $K$ class classification. Let $p$ be a vector of prior class probabilities,
$\alpha_i \in (-\infty, +\infty)$ be a worker ability parameter, $\beta_j \in (0, +\infty)$ be
an inverse task difficulty, $z_j$ be a latent variable representing the true task label, and $y^i_j$
be a worker response that we observe. The relationships between these variables and parameters according
to GLAD are represented by the following latent label model:

![GLAD latent label model](https://tlk.s3.yandex.net/crowd-kit/docs/glad_llm.png)


The prior probability of $z_j$ being equal to $c$ is
$$
\operatorname{Pr}(z_j = c) = p[c],
$$
and the probability distribution of the worker responses with the true label $c$ follows the
single coin Dawid-Skene model where the true label probability is a sigmoid function of the product of the
worker ability and the inverse task difficulty:
$$
\operatorname{Pr}(y^i_j = k | z_j = c) = \begin{cases}a(i, j), & k = c \\ \frac{1 - a(i,j)}{K-1}, & k \neq c\end{cases},
$$
where
$$
a(i,j) = \frac{1}{1 + \exp(-\alpha_i\beta_j)}.
$$

Parameters $p$, $\alpha$, $\beta$, and latent variables $z$ are optimized with the Expectation-Minimization algorithm:
1. **E-step**. Estimates the true task label probabilities using the alpha parameters of workers' abilities,
    the prior label probabilities, and the beta parameters of task difficulty.
2. **M-step**. Optimizes the alpha and beta parameters using the conjugate gradient method.


J. Whitehill, P. Ruvolo, T. Wu, J. Bergsma, and J. Movellan.
Whose Vote Should Count More: Optimal Integration of Labels from Labelers of Unknown Expertise.
*Proceedings of the 22nd International Conference on Neural Information Processing Systems*, 2009

<https://proceedings.neurips.cc/paper/2009/file/f899139df5e1059396431415e770c6dd-Paper.pdf>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The maximum number of EM iterations.</p>
`tol`|**float**|<p>The tolerance stopping criterion for iterative methods with a variable number of steps. The algorithm converges when the loss change is less than the `tol` parameter.</p>
`silent`|**bool**|<p>Specifies if the progress bar will be shown (false) or not (true).</p>
`labels_priors`|**Optional\[Series\]**|<p>The prior label probabilities.</p>
`alphas_priors_mean`|**Optional\[Series\]**|<p>The prior mean value of the alpha parameters.</p>
`betas_priors_mean`|**Optional\[Series\]**|<p>The prior mean value of the beta parameters.</p>
`m_step_max_iter`|**int**|<p>The maximum number of iterations of the conjugate gradient method in the M-step.</p>
`m_step_tol`|**float**|<p>The tolerance stopping criterion of the conjugate gradient method in the M-step.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>
`alphas_`|**Series**|<p>The alpha parameters of workers&#x27; abilities. The `pandas.Series` data is indexed by `worker` that contains the estimated alpha parameters.</p>
`betas_`|**Series**|<p>The beta parameters of task difficulty. The `pandas.Series` data is indexed by `task` that contains the estimated beta parameters.</p>
`loss_history_`|**List\[float\]**|<p>A list of loss values during training.</p>

**Examples:**


```python
from crowdkit.aggregation import GLAD
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
glad = GLAD()
result = glad.fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.glad.GLAD.fit.md)| Fits the model to the training data with the EM algorithm.
[fit_predict](crowdkit.aggregation.classification.glad.GLAD.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_proba](crowdkit.aggregation.classification.glad.GLAD.fit_predict_proba.md)| Fits the model to the training data and returns probability distributions of labels for each task.
