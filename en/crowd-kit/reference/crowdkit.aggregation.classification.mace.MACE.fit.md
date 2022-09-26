# fit
`crowdkit.aggregation.classification.mace.MACE.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0.rc4/crowdkit/aggregation/classification/mace.py#L145)

```python
fit(self, data: DataFrame)
```

Fits the MACE model.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; labeling results. A pandas.DataFrame containing `task`, `worker` and `label` columns.</p>

* **Returns:**

  The fitted MACE model.

* **Return type:**

  [MACE](crowdkit.aggregation.classification.mace.MACE.md)
