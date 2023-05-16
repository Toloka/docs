# fit
`crowdkit.aggregation.texts.rover.ROVER.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/texts/rover.py#L71)

```python
fit(self, data: DataFrame)
```

Fits the model. The aggregated results are saved to the `texts_` attribute.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; text outputs. A pandas.DataFrame containing `task`, `worker` and `text` columns.</p>

* **Returns:**

  self.

* **Return type:**

  [ROVER](crowdkit.aggregation.texts.rover.ROVER.md)
