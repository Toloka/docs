# predict_score
`crowdkit.aggregation.classification.m_msr.MMSR.predict_score` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/m_msr.py#L133)

```python
predict_score(self, data: DataFrame)
```

Returns the total sum of weights for each label when the model is fitted.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>

* **Returns:**

  The task label scores. The `pandas.DataFrame` data is indexed by `task`
so that `result.loc[task, label]` is a score of `label` for `task`.

* **Return type:**

  DataFrame
