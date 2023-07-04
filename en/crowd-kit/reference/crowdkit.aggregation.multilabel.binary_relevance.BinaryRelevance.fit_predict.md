# fit_predict
`crowdkit.aggregation.multilabel.binary_relevance.BinaryRelevance.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/multilabel/binary_relevance.py#L108)

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
is a list with the task's aggregated labels.

* **Return type:**

  Series
