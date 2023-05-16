# fit
`crowdkit.aggregation.classification.majority_vote.MajorityVote.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/majority_vote.py#L80)

```python
fit(
    self,
    data: DataFrame,
    skills: Optional[Series] = None
)
```

Fits the model to the training data.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>
`skills`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker and has the corresponding worker skill.</p>

* **Returns:**

  self.

* **Return type:**

  [MajorityVote](crowdkit.aggregation.classification.majority_vote.MajorityVote.md)
