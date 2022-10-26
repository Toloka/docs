# fit
`crowdkit.aggregation.classification.dawid_skene.OneCoinDawidSkene.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0/crowdkit/aggregation/classification/dawid_skene.py#L317)

```python
fit(self, data: DataFrame)
```

Fit the model through the EM-algorithm.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; labeling results. A pandas.DataFrame containing `task`, `worker` and `label` columns.</p>

* **Returns:**

  self.

* **Return type:**

  [OneCoinDawidSkene](crowdkit.aggregation.classification.dawid_skene.OneCoinDawidSkene.md)
