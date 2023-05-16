# fit_predict
`crowdkit.aggregation.classification.majority_vote.MajorityVote.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/majority_vote.py#L126)

```python
fit_predict(
    self,
    data: DataFrame,
    skills: Optional[Series] = None
)
```

Fits the model to the training data and returns the aggregated results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>
`skills`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker` and has the corresponding worker skill.</p>

* **Returns:**

  The task labels. The `pandas.Series` data is indexed by `task`
so that `labels.loc[task]` is the most likely true label of tasks.

* **Return type:**

  Series
