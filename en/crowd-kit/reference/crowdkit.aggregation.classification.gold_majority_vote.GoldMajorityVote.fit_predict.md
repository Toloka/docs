# fit_predict
`crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.fit_predict` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/gold_majority_vote.py#L120)

```python
fit_predict(
    self,
    data: DataFrame,
    true_labels: Series
)
```

Fits the model to the training data and returns the aggregated results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>The training dataset of workers&#x27; labeling results which is represented as the `pandas.DataFrame` data containing `task`, `worker`, and `label` columns.</p>
`true_labels`|**Series**|<p>The ground truth labels of tasks. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the task ground truth label.</p>

* **Returns:**

  The task labels. The `pandas.Series` data is indexed by `task`
so that `labels.loc[task]` is the most likely true label of tasks.

* **Return type:**

  Series
