# fit_predict
`crowdkit.aggregation.classification.m_msr.MMSR.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/m_msr.py#L147)

```python
fit_predict(self, data: DataFrame)
```

Fits the model to the training data and returns the aggregated results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>

* **Returns:**

  The task labels. The `pandas.Series` data is indexed by `task`
so that `labels.loc[task]` is the most likely true label of tasks.

* **Return type:**

  Series
