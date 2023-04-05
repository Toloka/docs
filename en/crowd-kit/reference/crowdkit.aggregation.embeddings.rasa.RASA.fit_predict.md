# fit_predict
`crowdkit.aggregation.embeddings.rasa.RASA.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/embeddings/rasa.py#L169)

```python
fit_predict(
    self,
    data: DataFrame,
    true_embeddings: Optional[Series] = None
)
```

Fits the model to the training data and returns the aggregated outputs.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The workers&#x27; outputs with their embeddings. The `pandas.DataFrame` data contains the `task`, `worker`, `output`, and `embedding` columns.</p>
`true_embeddings`|**Optional\[Series\]**|<p>The embeddings of the true task responses. The `pandas.Series` data is indexed by `task` and contains the corresponding embeddings. The multiple true embeddings are not supported for a single task.</p>

* **Returns:**

  The task embeddings and outputs.
The `pandas.DataFrame` data is indexed by `task` and has the `embedding` and `output` columns.

* **Return type:**

  DataFrame
