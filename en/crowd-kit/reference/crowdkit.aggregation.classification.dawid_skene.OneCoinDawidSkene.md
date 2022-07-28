# OneCoinDawidSkene
`crowdkit.aggregation.classification.dawid_skene.OneCoinDawidSkene` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0.rc2/crowdkit/aggregation/classification/dawid_skene.py#L220)

```python
OneCoinDawidSkene(
    self,
    n_iter: int = 100,
    tol: float = 1e-05
)
```

One-coin Dawid-Skene aggregation model.


This model works exactly like original Dawid-Skene model based on EM Algorithm except for workers' error calculation
on M-step of the algorithm.

First the workers' skills are calculated as their accuracy in accordance with labels probability.
Let $e^w$ be a worker's confusion (error) matrix of size $K \times K$ in case of $K$ class classification,
$p$ be a vector of prior classes probabilities, $z_j$ be a true task's label, and $y^w_j$ be a worker's
answer for the task $j$. Let s_{w} be a worker's skill (accuracy). Then the error
$$
e^w_{j,z_j}  = \begin{cases}
    s_{w} & y^w_j = z_j \\
    \frac{1 - s_{w}}{K - 1} & y^w_j \neq z_j
\end{cases}
$$

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The number of EM iterations.</p>
`labels_`|**Optional\[Series\]**|<p>Tasks&#x27; labels. A pandas.Series indexed by `task` such that `labels.loc[task]` is the tasks&#x27;s most likely true label.</p>
`probas_`|**DataFrame**|<p>Tasks&#x27; label probability distributions. A pandas.DataFrame indexed by `task` such that `result.loc[task, label]` is the probability of `task`&#x27;s true label to be equal to `label`. Each probability is between 0 and 1, all task&#x27;s probabilities should sum up to 1</p>
`priors_`|**Series**|<p>A prior label distribution. A pandas.Series indexed by labels and holding corresponding label&#x27;s probability of occurrence. Each probability is between 0 and 1, all probabilities should sum up to 1</p>
`errors_`|**DataFrame**|<p>Workers&#x27; error matrices. A pandas.DataFrame indexed by `worker` and `label` with a column for every label_id found in `data` such that `result.loc[worker, observed_label, true_label]` is the probability of `worker` producing an `observed_label` given that a task&#x27;s true label is `true_label`</p>
`skills_`|**Series**|<p>workers&#x27; skills. A pandas.Series index by workers and holding corresponding worker&#x27;s skill</p>

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
[fit](crowdkit.aggregation.classification.dawid_skene.OneCoinDawidSkene.fit.md)| Fit the model through the EM-algorithm.
