# GoldMajorityVote
`crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/classification/gold_majority_vote.py#L14)

```python
GoldMajorityVote(self)
```

The **Gold Majority Vote** model is used when a golden dataset (ground truth) exists for some tasks.


It calculates the probability of a correct label for each worker based on the golden set.
After that, the sum of the probabilities of each label is calculated for each task.
The correct label is the one with the greatest sum of the probabilities.

For example, you have 10 000 tasks completed by 3 000 different workers. And you have 100 tasks where you already
know the ground truth labels. First, you can call `fit` to calculate the percentage of correct labels for each worker.
And then call `predict` to calculate labels for your 10 000 tasks.

The following rules must be observed:
1. All workers must complete at least one task from the golden dataset.
2. All workers from the dataset that is submitted to `predict` must be included in the response dataset that is submitted to `fit`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`labels_`|**Optional\[Series\]**|<p>The task labels. The `pandas.Series` data is indexed by `task` so that `labels.loc[task]` is the most likely true label of tasks.</p>
`skills_`|**Optional\[Series\]**|<p>The workers&#x27; skills. The `pandas.Series` data is indexed by `worker` and has the corresponding worker skill.</p>
`probas_`|**Optional\[DataFrame\]**|<p>The probability distributions of task labels. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is the probability that the `task` true label is equal to `label`. Each probability is in the range from 0 to 1, all task probabilities must sum up to 1.</p>

**Examples:**


```python
import pandas as pd
from crowdkit.aggregation import GoldMajorityVote
df = pd.DataFrame(
    [
        ['t1', 'p1', 0],
        ['t1', 'p2', 0],
        ['t1', 'p3', 1],
        ['t2', 'p1', 1],
        ['t2', 'p2', 0],
        ['t2', 'p3', 1],
    ],
    columns=['task', 'worker', 'label']
)
true_labels = pd.Series({'t1': 0})
gold_mv = GoldMajorityVote()
result = gold_mv.fit_predict(df, true_labels)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.fit_predict.md)| Fits the model to the training data and returns the aggregated results.
[fit_predict_proba](crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.fit_predict_proba.md)| Fits the model to the training data and returns probability distributions of labels for each task.
[predict](crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.predict.md)| Predicts the true labels of tasks when the model is fitted.
[predict_proba](crowdkit.aggregation.classification.gold_majority_vote.GoldMajorityVote.predict_proba.md)| Returns probability distributions of labels for each task when the model is fitted.
