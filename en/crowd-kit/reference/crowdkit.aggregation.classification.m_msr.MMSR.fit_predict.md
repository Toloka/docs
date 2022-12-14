# fit_predict
`crowdkit.aggregation.classification.m_msr.MMSR.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.0/crowdkit/aggregation/classification/m_msr.py#L141)

```python
fit_predict(self, data: DataFrame)
```

Fit the model and return aggregated results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; labeling results. A pandas.DataFrame containing `task`, `worker` and `label` columns.</p>

* **Returns:**

  Tasks' labels.
A pandas.Series indexed by `task` such that `labels.loc[task]`
is the tasks's most likely true label.

* **Return type:**

  Series
