# KOS
`crowdkit.aggregation.classification.kos.KOS` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/kos.py#L14)

```python
KOS(
    self,
    n_iter: int = 100,
    random_state: int = 0
)
```

The **KOS** (Karger, Oh, and Shah 2011) aggregation model is an iterative algorithm that calculates the log-likelihood of the task being positive while modeling


the worker reliability.

Let $A_{ij}$ be a matrix of the responses of a worker $j$ on a task $i$.
If the worker $j$ does not respond to the task $i$, then $A_{ij} = 0$. Otherwise, $|A_{ij}| = 1$.
The algorithm operates on real-valued task messages $x_{i \rightarrow j}$  and
worker messages $y_{j \rightarrow i}$. A task message $x_{i \rightarrow j}$ represents
the log-likelihood of task $i$ being a positive task, and a worker message $y_{j \rightarrow i}$ represents
how reliable worker $j$ is.

At $k$-th iteration, the values are updated as follows:
$$
x_{i \rightarrow j}^{(k)} = \sum_{j^{'} \in \partial i \backslash j} A_{ij^{'}} y_{j^{'} \rightarrow i}^{(k-1)} \\
y_{j \rightarrow i}^{(k)} = \sum_{i^{'} \in \partial j \backslash i} A_{i^{'}j} x_{i^{'} \rightarrow j}^{(k-1)}
$$

David R. Karger, Sewoong Oh, and Devavrat Shah. Budget-Optimal Task Allocation for Reliable Crowdsourcing Systems.
*Operations Research 62.1 (2014)*, 1-38.

<https://arxiv.org/abs/1110.3564>

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_iter`|**int**|<p>The maximum number of iterations.</p>
`random_state`|**int**|<p>The state of the random number generator.</p>
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>

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
[fit](crowdkit.aggregation.classification.kos.KOS.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.classification.kos.KOS.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
