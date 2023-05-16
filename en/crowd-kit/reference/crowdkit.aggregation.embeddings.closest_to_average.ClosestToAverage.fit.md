# fit
`crowdkit.aggregation.embeddings.closest_to_average.ClosestToAverage.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/embeddings/closest_to_average.py#L39)

```python
fit(
    self,
    data: DataFrame,
    aggregated_embeddings: Optional[Series] = None,
    true_embeddings: Optional[Series] = None
)
```

Fits the model to the training data.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The workers&#x27; outputs with their embeddings. The `pandas.DataFrame` data contains the `task`, `worker`, `output`, and `embedding` columns.</p>
`aggregated_embeddings`|**Optional\[Series\]**|<p>The task aggregated embeddings. The `pandas.Series` data is indexed by `task` and contains the corresponding aggregated embeddings.</p>
`true_embeddings`|**Optional\[Series\]**|<p>The embeddings of the true task responses. The `pandas.Series` data is indexed by `task` and contains the corresponding embeddings. The multiple true embeddings are not supported for a single task.</p>

* **Returns:**

  self.

* **Return type:**

  [ClosestToAverage](crowdkit.aggregation.embeddings.closest_to_average.ClosestToAverage.md)
