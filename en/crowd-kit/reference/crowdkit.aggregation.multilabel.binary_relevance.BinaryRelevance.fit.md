# fit
`crowdkit.aggregation.multilabel.binary_relevance.BinaryRelevance.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.0/crowdkit/aggregation/multilabel/binary_relevance.py#L70)

```python
fit(self, data: DataFrame)
```

Fit the aggregators.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; labeling results. A pandas.DataFrame containing `task`, `worker` and `label` columns. &#x27;label&#x27; column should contain list of labels, e.g. [&#x27;tree&#x27;, &#x27;house&#x27;, &#x27;car&#x27;]</p>

* **Returns:**

  self.

* **Return type:**

  [BinaryRelevance](crowdkit.aggregation.multilabel.binary_relevance.BinaryRelevance.md)
