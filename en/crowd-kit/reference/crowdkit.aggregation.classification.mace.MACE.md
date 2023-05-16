# MACE
`crowdkit.aggregation.classification.mace.MACE` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/mace.py#L67)

```python
MACE(
    self,
    n_restarts: int = 10,
    n_iter: int = 50,
    method: str = 'vb',
    smoothing: float = 0.1,
    default_noise: float = 0.5,
    alpha: float = 0.5,
    beta: float = 0.5,
    random_state: int = 0,
    verbose: int = 0
)
```

The **Multi-Annotator Competence Estimation** (MACE) model is a probabilistic model that associates each worker with a label probability distribution.


A worker can be spamming on each task. If the worker is not spamming, they label a task correctly. If the worker is spamming, they answer according
to their probability distribution.

We assume that the correct label $T_i$ comes from a discrete uniform distribution. When a worker
annotates a task, they are spamming with probability
$\operatorname{Bernoulli}(1 - \theta_j)$. $S_{ij}$ specifies whether or not worker $j$ is spamming on instance $i$.
Thus, if the worker is not spamming on the task, i.e. $S_{ij} = 0$, their response is the true label, i.e. $A_{ij} = T_i$.
Otherwise, their response $A_{ij}$ is drawn from a multinomial distribution with parameter vector $\xi_j$.

![MACE latent label model](https://tlk.s3.yandex.net/crowd-kit/docs/mace_llm.png =500x630)

The model can be enhanced by adding the Beta prior on $\theta_j$ and the Diriclet
prior on $\xi_j$.

The marginal data likelihood is maximized with the Expectation-Maximization algorithm:
1. **E-step**. Performs `n_restarts` random restarts, and keeps the model with the best marginal data likelihood.
2. **M-step**. Smooths parameters by adding a fixed value `smoothing` to the fractional counts before normalizing.
3. **Variational M-step**. Employs Variational-Bayes (VB) training with symmetric Beta priors on $\theta_j$ and symmetric Dirichlet priors on the strategy parameters $\xi_j.

D. Hovy, T. Berg-Kirkpatrick, A. Vaswani and E. Hovy. Learning Whom to Trust with MACE.
In *Proceedings of NAACL-HLT*, Atlanta, GA, USA (2013), 1120–1130.

<https://aclanthology.org/N13-1132.pdf>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_restarts`|**int**|<p>The number of optimization runs of the algorithms. The final parameters are those that gave the best log likelihood. If one run takes too long, this parameter can be set to 1. Default: 10.</p>
`n_iter`|**int**|<p>The maximum number of EM iterations for each optimization run. Default: 50.</p>
`method`|**str**|<p>The method which is used for the M-step. Either &#x27;vb&#x27; or &#x27;em&#x27;. &#x27;vb&#x27; means optimization with Variational Bayes using priors. &#x27;em&#x27; means standard Expectation-Maximization algorithm. Default: &#x27;vb&#x27;.</p>
`smoothing`|**float**|<p>The smoothing parameter for the normalization. Default: 0.1.</p>
`default_noise`|**float**|<p>The default noise parameter for the initialization. Default: 0.5.</p>
`alpha`|**float**|<p>The prior parameter for the Beta distribution on $\theta_j$. Default: 0.5.</p>
`beta`|**float**|<p>The prior parameter for the Beta distribution on $\theta_j$. Default: 0.5.</p>
`random_state`|**int**|<p>The state of the random number generator. Default: 0.</p>
`verbose`|**int**|<p>Specifies if the progress will be printed or not: 0 — no progress bar, 1 — only for restarts, 2 — for both restarts and optimization. Default: 0.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>
`spamming_`|**...**|<p>The posterior distribution of workers&#x27; spamming states.</p>
`thetas_`|**...**|<p>The posterior distribution of workers&#x27; spamming labels.</p>
`theta_priors_`|**Optional\[...\]**|<p>The prior parameters for the Beta distribution on $\theta_j$.</p>
`strategy_priors_`|**Optional\[...\]**|<p>The prior parameters for the Diriclet distribution on $\xi_j$.</p>

**Examples:**


```python
from crowdkit.aggregation import MACE
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
mace = MACE()
result = mace.fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.mace.MACE.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.classification.mace.MACE.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_proba](crowdkit.aggregation.classification.mace.MACE.fit_predict_proba.md)| Fits the model to the training data and returns probability distributions of labels for each task.
