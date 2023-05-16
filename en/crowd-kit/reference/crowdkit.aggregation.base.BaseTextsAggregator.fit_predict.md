# fit_predict
`crowdkit.aggregation.base.BaseTextsAggregator.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/base/__init__.py#L135)

```python
fit_predict(self, data: DataFrame)
```

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; text outputs. A pandas.DataFrame containing `task`, `worker` and `text` columns.</p>

* **Returns:**

  Tasks' texts.
A pandas.Series indexed by `task` such that `result.loc[task, text]`
is the task's text.

* **Return type:**

  Series
