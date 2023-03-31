# fit
`crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/gold_majority_vote.py#L73)

```python
fit(
    self,
    data: DataFrame,
    true_labels: Series
)
```

Fits the model to the training data.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>
`true_labels`|**Series**|<p>The ground truth labels of tasks. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the task ground truth label.</p>

* **Returns:**

  self.

* **Return type:**

  [GoldMajorityVote](crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.md)
