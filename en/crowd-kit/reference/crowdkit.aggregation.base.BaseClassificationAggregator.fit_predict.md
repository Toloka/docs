# fit_predict
`crowdkit.aggregation.base.BaseClassificationAggregator.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.0/crowdkit/aggregation/base/__init__.py#L38)

```python
fit_predict(self, data: DataFrame)
```

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
