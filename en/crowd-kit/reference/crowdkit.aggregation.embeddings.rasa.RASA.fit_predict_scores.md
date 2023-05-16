# fit_predict_scores
`crowdkit.aggregation.embeddings.rasa.RASA.fit_predict_scores` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/embeddings/rasa.py#L150)

```python
fit_predict_scores(
    self,
    data: DataFrame,
    true_embeddings: Optional[Series] = None
)
```

Fits the model to the training data and returns the estimated scores.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The workers&#x27; outputs with their embeddings. The `pandas.DataFrame` data contains the `task`, `worker`, `output`, and `embedding` columns.</p>
`true_embeddings`|**Optional\[Series\]**|<p>The embeddings of the true task responses. The `pandas.Series` data is indexed by `task` and contains the corresponding embeddings. The multiple true embeddings are not supported for a single task.</p>

* **Returns:**

  The task label scores.
The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]`
is a score of `label` for `task`.

* **Return type:**

  DataFrame
