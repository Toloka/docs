# fit_predict
`crowdkit.aggregation.base.BaseEmbeddingsAggregator.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/base/__init__.py#L104)

```python
fit_predict(self, data: DataFrame)
```

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; outputs with their embeddings. A pandas.DataFrame containing `task`, `worker`, `output` and `embedding` columns.</p>

* **Returns:**

  Tasks' embeddings and outputs.
A pandas.DataFrame indexed by `task` with `embedding` and `output` columns.

* **Return type:**

  DataFrame
