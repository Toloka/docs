# fit
`crowdkit.aggregation.classification.m_msr.MMSR.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/m_msr.py#L103)

```python
fit(self, data: DataFrame)
```

Fits the model to the training data.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>

* **Returns:**

  self.

* **Return type:**

  [MMSR](crowdkit.aggregation.classification.m_msr.MMSR.md)
