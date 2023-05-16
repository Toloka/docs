# fit
`crowdkit.aggregation.classification.mace.MACE.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/mace.py#L148)

```python
fit(self, data: DataFrame)
```

Fits the model to the training data.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>

* **Returns:**

  The fitted MACE model.

* **Return type:**

  [MACE](crowdkit.aggregation.classification.mace.MACE.md)
