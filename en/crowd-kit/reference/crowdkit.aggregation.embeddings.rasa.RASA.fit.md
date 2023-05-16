# fit
`crowdkit.aggregation.embeddings.rasa.RASA.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/embeddings/rasa.py#L107)

```python
fit(
    self,
    data: DataFrame,
    true_embeddings: Optional[Series] = None
)
```

Fits the model to the training data.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The workers&#x27; outputs with their embeddings. The `pandas.DataFrame` data contains the `task`, `worker`, `output`, and `embedding` columns.</p>
`true_embeddings`|**Optional\[Series\]**|<p>The embeddings of the true task responses. The `pandas.Series` data is indexed by `task` and contains the corresponding embeddings. The multiple true embeddings are not supported for a single task.</p>

* **Returns:**

  self.

* **Return type:**

  [RASA](crowdkit.aggregation.embeddings.rasa.RASA.md)
