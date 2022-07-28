# fit_predict
`crowdkit.aggregation.classification.mace.MACE.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0.rc2/crowdkit/aggregation/classification/mace.py#L234)

```python
fit_predict(self, data: DataFrame)
```

Fits the MACE model and returns the labels.

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
