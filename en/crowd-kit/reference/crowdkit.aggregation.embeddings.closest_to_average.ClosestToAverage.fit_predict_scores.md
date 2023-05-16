# fit_predict_scores
`crowdkit.aggregation.embeddings.closest_to_average.ClosestToAverage.fit_predict_scores` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/embeddings/closest_to_average.py#L87)

```python
fit_predict_scores(
    self,
    data: DataFrame,
    aggregated_embeddings: Optional[Series] = None
)
```

Fits the model to the training data and returns the estimated scores.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The workers&#x27; outputs with their embeddings. The `pandas.DataFrame` data contains the `task`, `worker`, `output`, and `embedding` columns.</p>
`aggregated_embeddings`|**Optional\[Series\]**|<p>The task aggregated embeddings. The `pandas.Series` data is indexed by `task` and contains the corresponding aggregated embeddings.</p>

* **Returns:**

  The task label scores.
The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]`
is a score of `label` for `task`.

* **Return type:**

  DataFrame
