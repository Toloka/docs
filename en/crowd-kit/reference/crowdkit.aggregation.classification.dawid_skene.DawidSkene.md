# DawidSkene
`crowdkit.aggregation.classification.dawid_skene.DawidSkene` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/dawid_skene.py#L19)

```python
DawidSkene(
    self,
    n_iter: int = 100,
    tol: float = 1e-05
)
```

The **Dawid-Skene** aggregation model is a probabilistic model that parametrizes the expertise level of workers with confusion matrices.


Let $e^w$ be a worker confusion (error) matrix of size $K \times K$ in case of the $K$ class classification,
$p$ be a vector of prior class probabilities, $z_j$ be a true task label, and $y^w_j$ be a worker
response to the task $j$. The relationship between these parameters is represented by the following latent
label model.

![Dawid-Skene latent label model](https://tlk.s3.yandex.net/crowd-kit/docs/ds_llm.png)

Here the prior true label probability is
$$
\operatorname{Pr}(z_j = c) = p[c],
$$
and the probability distribution of the worker responses with the true label $c$ is represented by the
corresponding column of the error matrix:
$$
\operatorname{Pr}(y_j^w = k | z_j = c) = e^w[k, c].
$$

Parameters $p$, $e^w$, and latent variables $z$ are optimized with the Expectation-Maximization algorithm:
1. **E-step**. Estimates the true task label probabilities using the specified workers' responses,
    the prior label probabilities, and the workers' error probability matrix.
2. **M-step**. Estimates the workers' error probability matrix using the specified workers' responses and the true task label probabilities.

A. Philip Dawid and Allan M. Skene. Maximum Likelihood Estimation of Observer Error-Rates Using the EM Algorithm.
*Journal of the Royal Statistical Society. Series C (Applied Statistics), Vol. 28*, 1 (1979), 20–28.

<https://doi.org/10.2307/2346806>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The maximum number of EM iterations.</p>
`tol`|**float**|<p>The tolerance stopping criterion for iterative methods with a variable number of steps. The algorithm converges when the loss change is less than the `tol` parameter.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>
`priors_`|**Optional\[Series\]**|<p>The prior label distribution. The `pandas.Series` data is indexed by `label` and contains the probability of the corresponding label occurrence. Each probability is in the range from 0 to 1, all probabilities must sum up to 1.</p>
`errors_`|**Optional\[DataFrame\]**|<p>The workers&#x27; error matrices. The `pandas.DataFrame` data is indexed by `worker` and `label` with a column for every `label_id` found in `data` so that `result.loc[worker, observed_label, true_label]` is the probability that `worker` produces `observed_label`, given that the task true label is `true_label`.</p>
`loss_history_`|**List\[float\]**|<p>A list of loss values during training.</p>

**Examples:**


```python
from crowdkit.aggregation import DawidSkene
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
ds = DawidSkene(100)
result = ds.fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.dawid_skene.DawidSkene.fit.md)| Fits the model to the training data with the EM algorithm.
[fit_predict](crowdkit.aggregation.classification.dawid_skene.DawidSkene.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_proba](crowdkit.aggregation.classification.dawid_skene.DawidSkene.fit_predict_proba.md)| Fits the model to the training data and returns probability distributions of labels for each task.
