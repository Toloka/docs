# OneCoinDawidSkene
`crowdkit.aggregation.classification.dawid_skene.OneCoinDawidSkene` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/dawid_skene.py#L220)

```python
OneCoinDawidSkene(
    self,
    n_iter: int = 100,
    tol: float = 1e-05
)
```

The **one-coin Dawid-Skene** aggregation model works exactly the same as the original Dawid-Skene model based on the EM algorithm, except for calculating the workers' errors


at the M-step of the algorithm.

For the one-coin model, a worker confusion (error) matrix is parameterized by a single parameter $s_w$:
$$
e^w_{j,z_j}  = \begin{cases}
    s_{w} & y^w_j = z_j \\
    \frac{1 - s_{w}}{K - 1} & y^w_j \neq z_j
\end{cases}
$$
where $e^w$ is a worker confusion (error) matrix of size $K \times K$ in case of the $K$ class classification,
$z_j$ be a true task label, $y^w_j$ is a worker
response to the task $j$, and $s_w$ is a worker skill (accuracy).

In other words, the worker $w$ uses a single coin flip to decide their assignment. No matter what the true label is, the worker has the $s_w$ probability to assign the correct label, and
has the $1 − s_w$ probability to randomly assign an incorrect label. For the one-coin model, it
suffices to estimate $s_w$ for every worker $w$ and estimate $y^w_j$ for every task $j$. Because of its
simplicity, the one-coin model is easier to estimate and enjoys better convergence properties.

Parameters $p$, $e^w$, and latent variables $z$ are optimized with the Expectation-Maximization algorithm:
1. **E-step**. Estimates the true task label probabilities using the specified workers' responses,
the prior label probabilities, and the workers' error probability matrix.
2. **M-step**. Calculates a worker skill as their accuracy according to the label probability.
Then estimates the workers' error probability matrix by assigning user skills to error matrix row by row.

Y. Zhang, X. Chen, D. Zhou, and M. I. Jordan. Spectral methods meet EM: A provably optimal algorithm for crowdsourcing.
*Journal of Machine Learning Research. Vol. 17*, (2016), 1-44.

<https://doi.org/10.48550/arXiv.1406.3824>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The maximum number of EM iterations.</p>
`tol`|**float**|<p>The tolerance stopping criterion for iterative methods with a variable number of steps. The algorithm converges when the loss change is less than the `tol` parameter.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>
`priors_`|**Optional\[Series\]**|<p>The prior label distribution. The `pandas.Series` data is indexed by `label` and contains the probability of the corresponding label occurrence. Each probability is in the range from 0 to 1, all probabilities must sum up to 1.</p>
`errors_`|**Optional\[DataFrame\]**|<p>The workers&#x27; error matrices. The `pandas.DataFrame` data is indexed by `worker` and `label` with a column for every `label_id` found in `data` so that `result.loc[worker, observed_label, true_label]` is the probability that `worker` produces `observed_label`, given that the task true label is `true_label`.</p>
`skills_`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker` and has the corresponding worker skill.</p>
`loss_history_`|**List\[float\]**|<p>A list of loss values during training.</p>

**Examples:**


```python
from crowdkit.aggregation import OneCoinDawidSkene
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
hds = OneCoinDawidSkene(100)
result = hds.fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.dawid_skene.OneCoinDawidSkene.fit.md)| Fits the model to the training data with the EM algorithm.
