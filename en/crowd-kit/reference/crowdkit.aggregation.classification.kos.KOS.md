# KOS
`crowdkit.aggregation.classification.kos.KOS` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0.rc4/crowdkit/aggregation/classification/kos.py#L14)

```python
KOS(
    self,
    n_iter: int = 100,
    random_state: int = 0
)
```

Karger-Oh-Shah aggregation model.


Iterative algorithm that calculates the log-likelihood of the task being positive while modeling
the reliabilities of the workers.

Let $A_{ij}$ be a matrix of answers of worker $j$ on task $i$.
$A_{ij} = 0$ if worker $j$ didn't answer the task $i$, otherwise $|A_{ij}| = 1$.
The algorithm operates on real-valued task messages $x_{i \rightarrow j}$  and
worker messages $y_{j \rightarrow i}$. A task message $x_{i \rightarrow j}$ represents
the log-likelihood of task $i$ being a positive task, and a worker message $y_{j \rightarrow i}$ represents
how reliable worker $j$ is.

On iteration $k$ the values are updated as follows:
$$
x_{i \rightarrow j}^{(k)} = \sum_{j^{'} \in \partial i \backslash j} A_{ij^{'}} y_{j^{'} \rightarrow i}^{(k-1)} \\
y_{j \rightarrow i}^{(k)} = \sum_{i^{'} \in \partial j \backslash i} A_{i^{'}j} x_{i^{'} \rightarrow j}^{(k-1)}
$$

Karger, David R., Sewoong Oh, and Devavrat Shah. Budget-optimal task allocation for reliable crowdsourcing systems.
Operations Research 62.1 (2014): 1-24.

<https://arxiv.org/abs/1110.3564>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The number of iterations.</p>
`labels_`|**Optional\[Series\]**|<p>Tasks&#x27; labels. A pandas.Series indexed by `task` such that `labels.loc[task]` is the tasks&#x27;s most likely true label.</p>

**Examples:**


```python
from crowdkit.aggregation import KOS
from crowdkit.datasets import load_dataset
df, gt = load_dataset('relevance-2')
ds = KOS(10)
result = ds.fit_predict(df)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.kos.KOS.fit.md)| Fit the model.
[fit_predict](crowdkit.aggregation.classification.kos.KOS.fit_predict.md)| Fit the model and return aggregated results.
