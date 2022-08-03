# fit_predict_proba
`crowdkit.aggregation.classification.mace.MACE.fit_predict_proba` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0.rc2/crowdkit/aggregation/classification/mace.py#L249)

```python
fit_predict_proba(self, data: DataFrame)
```

Fits the MACE model and returns the label probability distributions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; labeling results. A pandas.DataFrame containing `task`, `worker` and `label` columns.</p>

* **Returns:**

  Tasks' label probability distributions.
A pandas.DataFrame indexed by `task` such that `result.loc[task, label]`
is the probability of `task`'s true label to be equal to `label`. Each
probability is between 0 and 1, all task's probabilities should sum up to 1

* **Return type:**

  DataFrame
