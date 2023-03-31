# fit
`crowdkit.aggregation.classification.glad.GLAD.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/glad.py#L279)

```python
fit(self, data: DataFrame)
```

Fits the model to the training data with the EM algorithm.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>

* **Returns:**

  self.

* **Return type:**

  [GLAD](crowdkit.aggregation.classification.glad.GLAD.md)
