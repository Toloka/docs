# fit_predict_proba
`crowdkit.aggregation.classification.mace.MACE.fit_predict_proba` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/mace.py#L251)

```python
fit_predict_proba(self, data: DataFrame)
```

Fits the model to the training data and returns probability distributions of labels for each task.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>

* **Returns:**

  Probability distributions of task labels.
The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`.
Each probability is in he range from 0 to 1, all task probabilities must sum up to 1.

* **Return type:**

  DataFrame
