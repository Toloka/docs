# fit
`crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/zero_based_skill.py#L79)

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

  [ZeroBasedSkill](crowdkit.aggregation.classification.zero_based_skill.ZeroBasedSkill.md)
