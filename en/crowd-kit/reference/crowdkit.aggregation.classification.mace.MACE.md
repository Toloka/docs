# MACE
`crowdkit.aggregation.classification.mace.MACE` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0.rc2/crowdkit/aggregation/classification/mace.py#L67)

```python
MACE(
    self,
    n_restarts: int = 10,
    n_iter: int = 50,
    method: str = 'vb',
    default_noise: float = 0.5,
    alpha: float = 0.5,
    beta: float = 0.5,
    random_state: int = 0,
    verbose: int = 0
)
```

Multi-Annotator Competence Estimation.


Probabilistic model that associates each worker with a probability distribution over the labels.
For each task, a worker might be in a spamming or not spamming state. If the worker is not
spamming, they yield a correct label. If the worker is spamming, they answer according
to their probability distribution.

We assume that the correct label $T_i$ comes from a discrete uniform distribution. When a worker
annotates the task, they are in the spamming state with probability
$\operatorname{Bernoulli}(1 - \theta_w)$. So, if their state $s_w = 0$, their response
$A_{iw} = T_i$. Otherwise, their response $A_{iw}$ is drawn from a multinomial
distribution with parameters $\xi_w$.

![MACE latent label model](https://tlk.s3.yandex.net/crowd-kit/docs/mace_llm.png)

The model can be enhanced by adding a Beta prior over $\theta_w$ and Diriclet
prior over $\xi_w$.

D. Hovy, T. Berg-Kirkpatrick, A. Vaswani and E. Hovy. Learning Whom to Trust with MACE.
In *Proceedings of NAACL-HLT*, Atlanta, GA, USA (2013), 1120–1130.

<https://aclanthology.org/N13-1132.pdf>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_restarts`|**int**|<p>The of algorithms optimization runs. The final parameters are ones that gave the best log likelihood. When a single run takes too long, it is fine to set this parameter to 1. Default: 10.</p>
`n_iter`|**int**|<p>The number of EM iterations for each optimization run. Default: 50.</p>
`method`|**str**|<p>The method to use for the M-step. Either &#x27;vb&#x27; or &#x27;em&#x27;. &#x27;vb&#x27; means optimization through variational Bayes using priors. &#x27;em&#x27; stands for straightforward Expectation-Maximization. Default: &#x27;vb&#x27;.</p>
`smoothing`|**-**|<p>The smoothing parameter for the normalization. Default: 0.1.</p>
`alpha`|**float**|<p>The prior parameter for the Beta distribution over $\theta_w$. Default: 0.5.</p>
`beta`|**float**|<p>The prior parameter for the Beta distribution over $\theta_w$. Default: 0.5.</p>
`default_noise`|**float**|<p>The default noise parameter for the initialization. Default: 0.5.</p>
`verbose`|**int**|<p>Whether to print progress. 0 — no progress bar, 1 — only for restarts, 2 — for both restarts and optimization. Default: 0.</p>
`labels_`|**Optional\[Series\]**|<p>Tasks&#x27; labels. A pandas.Series indexed by `task` such that `labels.loc[task]` is the tasks&#x27;s most likely true label.</p>
`probas_`|**Optional\[DataFrame\]**|<p>Tasks&#x27; label probability distributions. A pandas.DataFrame indexed by `task` such that `result.loc[task, label]` is the probability of `task`&#x27;s true label to be equal to `label`. Each probability is between 0 and 1, all task&#x27;s probabilities should sum up to 1</p>
`spamming_`|**ndarray**|<p>Posterior distribution of workers&#x27; spamming states.</p>
`thetas_`|**ndarray**|<p>Posterior distribution of workers&#x27; spamming labels.</p>

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
[fit](crowdkit.aggregation.classification.mace.MACE.fit.md)| Fits the MACE model.
[fit_predict](crowdkit.aggregation.classification.mace.MACE.fit_predict.md)| Fits the MACE model and returns the labels.
[fit_predict_proba](crowdkit.aggregation.classification.mace.MACE.fit_predict_proba.md)| Fits the MACE model and returns the label probability distributions.
